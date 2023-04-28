# Hello Tophat!

This chapter shows you how to make a simple hello world program in tophat.
Firstly make a new folder.  In that folder create a file called `main.um`, open
it in your favorite text editor and write the following in:

```umka
import (
	"canvas.um"
	"th.um"
	"window.um"
)

fn main() {
	window.setup("Hello tophat!", 600, 600)

	for window.cycle() {
		canvas.drawText("Hello tophat!", th.Vf2{ 1, 1 }, th.black, 2)
	}
}
```

Now run the file.  On linux you would `cd` into the directory and run `tophat`.
On windows, open `tophat` and choose the directory or make a shortcut to tophat
in the folder, so you can run the game by just double-clicking it.

Does everything work? Great! Is there a problem? Contact me at
[marek@mrms.cz](mailto:marek@mrms.cz).

Now let's explain all the parts of the example.

```umka
import (
	"canvas.um"
	"th.um"
	"window.um"
)
```

The import statement imports all the modules you will need. The strings in the
`import` statements are file-paths, but all the modules included in the example
are tophat builtin modules.  This means you can import them even though they
aren't on the file system.  All modules have their documentation available
[here](api/README.md).

```umka
fn main() {
```

This declares the `main` function. It is the main entry point of your game.

```umka
	window.setup("Hello tophat!", 600, 600)
```

This function call creates a window. It will set the title to "Hello tophat!"
and the dimensions to 600x600.

```umka
	for window.cycle() {
```

The `for` cycle is the main loop of your game. The `window.cycle` call is very
important - it ends the current frame, draws stuff to the screen and reads
input. If you don't call this, nothing will work. The function returns `true`
while the window is open. This way you can put deinitialization code after the
loop.

```umka
		canvas.drawText("Hello tophat!", th.Vf2{ 1, 1 }, th.black, 2)
```

This function does the actual drawing.
