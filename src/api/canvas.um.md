## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L0)

```
```

Canvas library allowing for drawing basic shapes. Coordinates are based on
the screen.


## [fn drawText](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L9)

```
fn drawText*(text: str, pos: th.Vf2, color: uint32, size: th.fu) {
```

Draws a basic pixel text. Only ascii is supported.


## [fn textSize](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L15)

```
fn textSize*(text: str, scale: th.fu): th.Vf2 {
```

Returns the size of text taken by an equivalent drawText call.


## [fn drawRect](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L40)

```
fn drawRect*(color: uint32, r: rect.Rect) {
```

Draws a Rectangle.


## [fn drawLine](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L47)

```
fn drawLine*(color: uint32, b, e: th.Vf2, thickness: th.fu) {
```

Draws a line.


## [fn drawQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/canvas.um#L54)

```
fn drawQuad*(color: uint32, q: th.Quad) {
```

Draws a convex quad.


