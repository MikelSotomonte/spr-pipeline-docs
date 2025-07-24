---
{"dg-publish":true,"permalink":"/thoughts/assembly/"}
---

Allowed software: [[thoughts/Houdini\|Houdini]].

At least for now, assembly refers to the department where all of the other departments for the [[thoughts/asset\|asset]] type are combined into one [[thoughts/USD\|USD]] file. This is then sublayered into the [[shot\|shot]] departments..

The asset hierarchy for [[character\|character]], which is the most complex, is this: 

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

Add a primitive [[thoughts/USD\|USD]] node with the text above at the top of the [[thoughts/solaris\|solaris]] hierarchy.