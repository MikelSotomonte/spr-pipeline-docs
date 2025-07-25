---
{"dg-publish":true,"dg-path":"thoughts/scaling issues.md","permalink":"/thoughts/scaling-issues/","hide":true}
---

Different [[sprouts/thoughts/software/software\|software]] have a different scale. For example, [[sprouts/thoughts/software/Blender\|Blender]] and [[sprouts/thoughts/software/Houdini\|Houdini]] work in meters, [[sprouts/thoughts/software/Maya\|Maya]] works in centimeters, and [[sprouts/thoughts/software/Marvelous\|Marvelous]] in millimeters. Why? Idk man, but it's a pain. 

I am mostly concerned about Maya and Houdini playing nicely together. Because of houdini's nature, and because it comes last in the 3d pipeline, we will be doing all of the scaling fixes in houdini.

In 3d, there are different ways of scaling a model. You can either scale the object itself, or you can move all of the vertices to scale the object. These two operations are not the same for multiple reasons. For example, applying a bevel to a non-uniformly scaled object will result in a skewed bevel, because the bevel gets applied first, and then the scaling of the model. 

In [[sprouts/thoughts/solaris\|solaris]], let's say that we are doing the assembly of a character, and because the model is coming from maya, the scale is 100 times too big. We can either add a transform set to 0.01 to the root primitive of the character, or we can use a sop modify and scale the polygons by the same factor. You might think both of these will be fine, but this is not the case. While the usd transform gets saved into the .usd as a transform, the vertex transforms get baked down, it's just a smaller model. So when the animation gets imported, and the positions of the points get overridden (so that the animation gets applied), if we scaled the vertices, the positions will just get replaced and still be 100 times too big. If instead, we used a usd transform, the position will get overridden first, and then scaled down to 0.01. Success! Although it complicates the usd layer stack a little bit, this is the best solution so far. Also more performant because there is no need to convert from usd to houdini geometry, and there is no need to unpack or convert the model.

Cameras don't have vertices, so you can only change its transforms (location, rotation, scale).
Scaling the camera is a big no-no, as it will mess with the math that allows rendering and it can give unexpected results. The solution is to multiply the coordinates of the location of the camera instead. This is a script that does exactly that, add it to an attribute wrangle in solaris.

```
string primpath = s@primpath; // Read/process/write with time support vector translate = usd_attrib(0, primpath, "xformOp:translate", @Frame); translate *= 0.01; usd_setattrib(0, primpath, "xformOp:translate", translate);
```
