# Keyboard input

Getting keyboard and mouse input in tophat is very simple. It is done using the
[input.um](/thdocs/input.html) module.

There are two ways to get keyboard input in tophat. The `is*` functions and the
`getStr` function. The former returns info about a physical key on the
keyboard. `getStr` returns a string typed by the user last cycle.

Example:

```umka
for i:=0; i < 256; i++ {
	if input.isPressed(char(i)) {
		printf("%d is pressed\n", i)
	}
}

printf("the user wrote: %s\n", input.getStr())
```

Getting mouse input is also simple. Mouse buttons act as normal keys, so you
can use the `is*` fuctions. Mouse position can be retrieved using the
`getMousePos` function.

```umka
import (
	"input.um"
	"signal.um"
	"th.um"
	"window.um"
)

fn init*() {
	window.setup()

	window.onFrame.register({
		for i:=0; i < 256; i++ {
			if input.isPressed(char(i)) {
				printf("%d is pressed\n", i)
			}
		}

		printf("the user wrote: %s\n", input.getStr())
		
		printf("the cursor is at %s\n", repr(input.getMousePos()))
	})
}
```
