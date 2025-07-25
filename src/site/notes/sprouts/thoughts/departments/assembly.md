---
{"dg-publish":true,"dg-path":"thoughts/departments/assembly.md","permalink":"/thoughts/departments/assembly/","hide":true}
---

#pipeline/departments/asset

At least for now, assembly refers to the department where all of the other departments for the [[sprouts/thoughts/asset\|asset]] type are combined into one [[sprouts/thoughts/USD\|USD]] file. This is then sublayered into the [[sprouts/thoughts/shot\|shot]] departments..

The asset hierarchy for [[sprouts/thoughts/character\|character]], which is the most complex, is this: 

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