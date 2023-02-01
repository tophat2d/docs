# Drawing text

There are two main ways of drawing text on the screen. The first one is the
drawText function from [canvas.um](/api/canvas.um.md). It draws a simple 5\*5
pixel text. It is useful for debugging, since it's easy to use, but doesn't
produce good looking results and only supports ASCII. This makes it unfit for
production use.

The second one uses tophat's [font.um](/api/font.um.md) module,
which provides functions for operating with TrueType fonts. You can obtain
a `Font` like this:

```
f := font.load("unifont.ttf", 32)
```

Then you can just use it's `draw` method to draw text. Example:

```
f.draw("Hello tophat", th.Vf2{20, 20}, th.green)
```

```
import (
	"canvas.um"
	"font.um"
	"th.um"
	"window.um"
)

fn main() {
	window.setup()

	f := font.load("unifont.ttf", 32, font.filteringNearest)

	for window.cycle() {
		canvas.drawText("Hello tophat using canvas.um", th.Vf2{1, 1}, th.black, 1)
		f.draw("Hello tophat using unifont", th.Vf2{1, 7}, th.black, 1)
	}
}
```
