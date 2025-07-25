---
{"dg-publish":true,"dg-path":"sublayer.md","permalink":"/sublayer/"}
---

#usd 
Sublayer is just a single usd [[sprouts/thoughts/layer\|layer]], so a sublayer is a type of layer.

For instance, we can have a chair layer made of different sublayers.
> [!Quote] chair.usd
> > [!Quote] chair_material.usd
>
> > [!Quote] chair_model.usd

In this example, `chair` is a layer, and `chair material` and `chair model` are sublayers.

`chair.usd` will be a very small file, because it will only point to the chair_material.usd and chair_model.usd files on disk, it might look something like this when seen as text:
```
(
    subLayers = [
		@../publish/Lookdev/chair_material_v001.usd@,
		@../publish/Modeling/chair_model_v003.usd@
    ]
)
```

Please note that in our pipeline, there won't be a [[sprouts/thoughts/lookdev\|lookdev]] sublayer, because it will be done in the [[sprouts/thoughts/assembly\|assembly]] department. This is just an example of how layering [[sprouts/thoughts/USD\|USD]] works.

More info: [[sprouts/thoughts/layer\|layer]]