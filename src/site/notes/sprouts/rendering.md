---
{"dg-publish":true,"permalink":"/sprouts/rendering/","hide":true}
---


#pipeline/departments/shot 
For rendering, there are some things to decide, and some things I want to highlingt. 

It is important to cache one extra frame before and another extra frame after the render frame range, to have enough info for the motion blur to work correctly the first and last frames of the render. We might also render with handles (extra frames before and after the shot, to have some wiggle room in the edit). I think 4-8 frames will be ideal.

A question I have is if we will do the depth of field in-render or in comp, and if we will use DEEP for everything, or just for special cases like an explosion with smoke. Probably the latter.
