# Tophat tips

> The API reference is your best friend.

> Rotations are in degrees.

> Assets paths are prefixed with the `dir`. That is `./` by default, but you
> can specify it using the `dir` flag.

> You can get last frame length from `th.delta`.

> Images are passed by reference, but you can make copies using the `copy`
> method.

> Signals make it simple to create large projects.

> Resizing the window won't change how the game is displayed - the viewport
> stays the same. The viewport size is in the `window.wp` variable. You can
> change it to your liking.

> The API reference is accessible from your terminal like this:
> ```
> $ curl https://docs.th.mrms.cz/api/module.um.md
> ```
>
> I recommend making an alias for this.

> You can center a rectangle `i` inside rectangle `o` using this formula:
> ```
>	i.x = o.x + (o.w - i.w) / 2
>	i.y = o.y + (o.h - i.h) / 2
> ```

> `particles.um` are cool, but hard to use. Annoy me at my
> [email](mailto:marek@mrms.cz) to make them easier to use.

> Dimensions of one `canvas.drawText` character is 5x5 px, and the character
> spacing is 1px.

> One sound can't be played more than once at a time, unless you use the
> `start` method.

> All `input.um` functions except for `getStr` are independant of the current
> keyboard layout.

> `input.getMouseDelta` works even if the cursor is frozen using
> `window.freezeCursor`
