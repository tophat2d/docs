# ui.um tutorial

You can see the result of this tutorial
[here](https://tophat2d.dev/examples/ui).

```umka
var gui: ui.Gui
var tbName, tbPwd: ui.TextBox
```

Here we declare three variables. `gui` is of the type `ui.Gui`, which holds the
whole UI instance. `tbName` and `tbPwd` are both textboxes, which will be used
later to get input from the user.

```umka
	gui = ui.mk({ 0, 0, 200, 200 }, ui.getDefaultStyle())
```

This initializes the UI instance. The first argument is the rect the gui will
occupy, the second is the style used. For now you can use tophat's default
style available using `ui.getDefaultStyle()`.

```umka
		layout := ui.LayoutFn{
            ...
		}
```

This is the layout function, which builds the UI by calling methods on the
`gui` struct. It is ran two times - first time to evaluate user input and
second time to draw the user interface.

```umka
			gui.stack({ padding: 10 })
```

First we use the `stack` container. It puts all the other elements on top of
each other. You can also apply padding to it.

```umka
			gui.box({
				dimension: 10,
				dir: ui.BoxDirectionDown,
				growType: ui.BoxGrowDimension })
```

Then we initialize a `box` container. This container puts all the elements next
to each other. The configuration specifies three things:

* `dir` - the direction the elements are put in, in this case they will go from
  up to down
* `growType` - specifies the way box will move the elements
* `dimension` - this specifies the number of pixels to grow by. This is needed
  as `ui.BoxGrowDimension` is specified

```umka
				gui.label("User name:", { centerY: true })
				gui.textBox(&tbName)

				gui.label("Password:", { centerY: true })
				gui.textBox(&tbPwd)
```

Now we can add the textboxes into the container.

```umka
			gui.dupStyle()
			gui.getStyle().containerBox.color = 0

			gui.box({
				dimension: 10,
				dir: ui.BoxDirectionUp,
				growType: ui.BoxGrowDimension })
			gui.box({
				subdivisions: 2,
				dir: ui.BoxDirectionRight,
				growType: ui.BoxGrowSubdivision })
```

This initializes the container for the buttons. Since we want the buttons to be
on the bottom, a box with `ui.BoxDirectionUp` is put onto the stack. However
the style dictates, that a box shall have a gray background, which needs to be
removed as not to cover the textboxes. Then we push another box. It grows to
the right and uses the subdivision grow type. We specify that there will be two
elements in it.

```umka
				if gui.qbutton("Cancel") {
					window.quit()
				}

				if gui.qbutton("Login") {
					printf("Login: %s %s\n",
						tbName.buffer, tbPwd.buffer)
				}
```

Now we can just add the two buttons. We use the method `qbutton`, which adds a
button with a label.


```umka
			gui.popContainer()
			gui.popContainer()

			gui.popStyle()

			gui.popContainer()
		}
```

Now we have to pop all the styles and containers. At the end of the layout
function, `len(gui.container)` should equal 1.

```umka
		gui.eval(layout)
		gui.draw(layout)
```

This applies the layout with our UI instance `gui`.

* * *

Full code:

```umka
import (
	"th.um"
	"ui.um"
	"window.um"
)

var gui: ui.Gui
var tbName, tbPwd: ui.TextBox

fn init*() {
	window.setup("ui.um tutorial", 600, 600)
	window.setViewport({ 200, 200 })

	gui = ui.mk({ 0, 0, 200, 200 }, ui.getDefaultStyle())

	window.onFrame.register({
		layout := ui.LayoutFn{
			gui.stack({ padding: 10 })

			gui.box({
				dimension: 10,
				dir: ui.BoxDirectionDown,
				growType: ui.BoxGrowDimension })

				gui.label("User name:", { centerY: true })
				gui.textBox(&tbName)

				gui.label("Password:", { centerY: true })
				gui.textBox(&tbPwd)
			gui.popContainer()

			gui.dupStyle()
			gui.getStyle().containerBox.color = 0

			gui.box({
				dimension: 10,
				dir: ui.BoxDirectionUp,
				growType: ui.BoxGrowDimension })
			gui.box({
				subdivisions: 2,
				dir: ui.BoxDirectionRight,
				growType: ui.BoxGrowSubdivision })

				if gui.qbutton("Cancel") {
					window.quit()
				}

				if gui.qbutton("Login") {
					printf("Login: %s %s\n",
						tbName.buffer, tbPwd.buffer)
				}

			gui.popContainer()
			gui.popContainer()

			gui.popStyle()

			gui.popContainer()
		}
		
		gui.eval(layout)
		gui.draw(layout)
	})
}
```
