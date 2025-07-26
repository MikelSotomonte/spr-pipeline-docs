---
{"dg-publish":true,"dg-path":"assembly.md","permalink":"/assembly/","hide":true}
---

#pipeline/departments/asset

At least for now, assembly refers to the department where all of the other departments for the [[sprouts/thoughts/asset\|asset]] type are combined into one [[sprouts/thoughts/USD\|USD]] file. This is then [[sprouts/thoughts/sublayer\|sublayered]] into the [[sprouts/thoughts/shot\|shot]] departments.

The asset hierarchy for [[sprouts/thoughts/character\|character]], which is fairly complex, is this: 

```
/fx
/lights
/materials
/geo/body/skin
/geo/body/eyes
/geo/clothes/cloth/gmt
/geo/clothes/cloth/render
/geo/clothes/rigid
/geo/hair/head/groom/
/geo/hair/head/sim/anim_guides
/geo/hair/face/eyebrows
/geo/hair/face/eyelashes
```

Add a primitive [[sprouts/thoughts/USD\|USD]] node with the text above at the top of the [[sprouts/thoughts/solaris\|solaris]] hierarchy.

For simplicity, all of the different [[sprouts/thoughts/layer\|layers]] will be baked down (flattened) into a single assembly layer. This is not the best for big studios, but it will simplify the pipeline a little bit for us, as it will allow us to do a lot of fixes on the geo level here (transfering skin attributes to hair for example) that would get annoying to keep track of if we didn't flatten.

