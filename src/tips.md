# Tophat tips

> The API reference is your best friend.

> Rotations are in degrees.

> Assets paths are prefixed with the `dir`. That is `./` by default, but you
> can specify it using the `dir` flag. If you prefix a path with `raw://`, it
> will not be changed by tophat.

> You can get last frame length from `th.delta`. This is useful for making your
> game FPS independant. A good rule of thumb is to multiply any kind of
> movement by the `th.delta` value.

> Resizing the window won't change how the game is displayed - the viewport
> stays the same. The viewport size is in the `window.wp` variable. You can
> change it to your liking.

> Dimensions of one `canvas.drawText` character is 5x5 px, and the character
> spacing is 1px.

> `input.getMouseDelta` works even if the cursor is frozen using
> `window.freezeCursor`
