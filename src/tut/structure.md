# Program structure

Your every project has to have a main file.  By default that is `main.um`, but
that can be changed using the `main` flag.  In your main file you need to
declare an `init` function, which **needs** to be exported.  If it isn't
exported, you will receive this error:

```
error: <PWD>/tophat_main.um (4, 11): Unknown identifier init
```

In this function, you can set up the window, load resources and register to the
`window.onFrame` [signal](/api/signal.um.md).  This signal is emitted on every
frame.  The following script will print "init" when it is launched and then
follow up by printing "frame" on every frame.

```umka
import (
    "signal.um"
    "window.um"
)

fn init*() {
    window.setup("Main file structure example")

    printf("init\n")

    window.onFrame.register(signal.Callback{
        printf("frame\n")
    }, null)
}
```
