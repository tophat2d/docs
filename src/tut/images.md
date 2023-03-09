# Loading and drawing images

First you need to import the [image.um](/api/image.um.md) module, which houses
all sorts of image functions. We are interested in `image.load`. It takes a
path to an image, which it loads and then returns. Example:

```
apple := image.load("gfx/apple.png")
```

You can check the image using the `validate` method.

```
if !apple.validate() {
	error("Could not load gfx/apple.png")
}
```

That's all. The image is now ready to be drawn. You can do that using it's draw
method. You need to pass it a transform.

```
apple.draw(th.Transform{
	p: th.Vf2{5, 20},
	s: th.Vf2{1, 1},
	r: 45 })
```

This draws the image at position [5, 20] rotated by 45 degrees.

Full example:

```
import (
	"image.um"
    "signal.um"
	"th.um"
	"window.um"
)

var (
    apple: image.Image
)

fn init*() {
	window.setup()

	apple = image.load("gfx/apple.png")
	if !apple.validate() {
		error("Could not load gfx/apple.png")
	}

	window.onFrame.register(signal.Callback{
		apple.draw(th.Transform{
			p: th.Vf2{5, 20},
			s: th.Vf2{1, 1},
			r: 45 })
	}, null)
}
```

