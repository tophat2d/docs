# Sprite sheet animations

This tutorial shows how to turn your spritesheets into animation.  This is a
builtin tophat feature, which makes this a very easy task.

We will need to declare these global variables:

```
var (
	spriteSheet: image.Image
	atl: atlas.Atlas
	anm: anim.Anim
)
```

First you have to load the image with your spritesheet:

```
	spriteSheet = image.load("spritesheet.png")
```

We then use the image to create an [atlas](/api/atlas.um.md).  An atlas is used
to operate with images that store subimages in a grid.  The first argument to
the mk function is the image we will create the atlas from.  The second
argument are the dimensions of the atlas.

```
	atl = atlas.mk(spriteSheet, th.Vf2{ 6, 1 })
```

The atlas is then used to create an [animation](/api/anim.um.md).  The first
argument is the atlas with the spritesheet.  The second argument is the fps
count.  You can also add optional arguments specifying start and end frame and
the start offset.

```
	anm = anim.mk(atl, 1)
```

We now have the animation ready.  Now we just have to call it's `animate`
method.  The only argument it the time.  We can use just `th.time` in this
case.

```
		anm.animate(th.time)
```

The `animate` method uses the the base image's `crop` method to select the
current frame.  This means we can now just draw the image.

```
		spriteSheet.draw(th.mkTransform(th.vf2f(1)))
```

* * *

Full program:

```
import (
	"anim.um"
	"atlas.um"
	"image.um"
	"signal.um"
	"th.um"
	"window.um"
)

var (
	spriteSheet: image.Image
	atl: atlas.Atlas
	anm: anim.Anim
)

fn init*() {
	window.setup("animation example", 500, 500)
	window.setViewport(th.Vf2{ 5, 5 })

	spriteSheet = image.load("spritesheet.png")
	atl = atlas.mk(spriteSheet, th.Vf2{ 6, 1 })
	anm = anim.mk(atl, 1)

	window.onFrame.register(signal.Callback{
		anm.animate(th.time)
		spriteSheet.draw(th.mkTransform(th.vf2f(1)))
	}, null)
}
```

You can see the full result [here](https://tophat2d.dev/examples/anim-tut).
