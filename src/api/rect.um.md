## [struct Rect](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L4)

```
type Rect* = struct {
	x, y, w, h: th.fu
}
```

A set of points representing a rectangle.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L10)

```
fn mk*(x, y, w, h: th.fu): Rect {
```



## [fn Rect.toWorld](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L20)

```
fn (r: ^Rect) toWorld*(p: th.Vf2): th.Vf2 {
```

translates screen coordinates to world coordinates with cam r


## [fn Rect.toScreen](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L26)

```
fn (r: ^Rect) toScreen*(p: th.Vf2): th.Vf2 {
```

translates world coordinates to screen coordinates with cam r


## [fn Rect.getPos](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L32)

```
fn (r: ^Rect) getPos*(): th.Vf2 {
```



## [fn Rect.getDims](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L37)

```
fn (r: ^Rect) getDims*(): th.Vf2 {
```



## [fn Rect.getEnd](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L42)

```
fn (r: ^Rect) getEnd*(): th.Vf2 {
```

returns where the second point of the rectangle lies.


## [fn Rect.transformed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L49)

```
fn (r: ^Rect) transformed*(t: th.Transform): th.Quad {
```

Transforms a rect into a quad.
Order:
1. scale
2. rotation
3. position


## [fn Rect.shrink](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L61)

```
fn (r: ^Rect) shrink*(p: th.Vf2): Rect {
```

Shrink the rectangle by `p` pixels from all sides.


## [fn Rect.shift](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L67)

```
fn (r: ^Rect) shift*(p: th.Vf2): Rect {
```

Shift the rectangle by `p` pixels.


## [fn Rect.scale](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/rect.um#L73)

```
fn (r: ^Rect) scale*(p: th.Vf2): Rect {
```

Multiply the dimensions by `p`


