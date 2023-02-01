## [opaque Image](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L4)

```
type Image* = struct{ _: ^struct{} }
```

Represents a drawable image. It is an opaque structure.
Images support a color filter. It is applied by multiplying the color
of each pixel with the filter.


## [fn load](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L12)

```
fn load*(path: str): Image {
```

Loads an image at path.


## [fn Image.flipv](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L21)

```
fn (i: ^Image) flipv*(flip: bool) {
```

Flips image on it's vertical axis.


## [fn Image.fliph](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L28)

```
fn (i: ^Image) fliph*(flip: bool) {
```

Flips image on it's horizontal axis.


## [fn Image.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L35)

```
fn (i: ^Image) draw*(t: th.Transform, color: uint32 = th.white) {
```

Draws the image in screen coordinates. It transforms it with t and
applies color as a color filter.


## [fn Image.drawNinepatch](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L44)

```
fn (i: ^Image) drawNinepatch*(outer, inner, dest: rect.Rect, color: uint32 = th.white) {
```

Draws "nine-patch" image.
`outer` specifies the texture coordinates of the outer rect of source image,
`inner` specifies coordinates of inner rect of source image, positioned relative to `outer`.
You can tint with `color`.


## [fn Image.drawOnQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L54)

```
fn (i: ^Image) drawOnQuad*(q: th.Quad, color: uint32 = th.white) {
```

Draws the image on top of a quad with corners of the image positioned
on the verticies of the quad.


## [fn Image.validate](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L61)

```
fn (i: ^Image) validate*(): bool {
```

Returns true, if i's handle points to an image.


## [fn Image.getDims](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L68)

```
fn (i: ^Image) getDims*(): th.Vf2 {
```

Returns width and heigth.


## [fn Image.crop](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L77)

```
fn (i: ^Image) crop*(tl, br: th.Vf2) {
```

Crops an image. Coordinates are between 0, 0 (top left) and
1, 1 (bottom right)


## [fn Image.cropQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L85)

```
fn (i: ^Image) cropQuad*(q: th.Quad) {
```

Crop an image using a quad.


## [fn Image.getCropQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L92)

```
fn (i: ^Image) getCropQuad*(): th.Quad {
```

Crop an image using a quad.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L101)

```
fn mk*(data: []uint32, dm: th.Vf2): Image {
```

Creates an image from raw data.


## [fn Image.copy](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L110)

```
fn (i: ^Image) copy*(): Image {
```

Copies image into a new one.


## [fn Image.setfilter](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L120)

```
fn (i: ^Image) setfilter*(filter: int) {
```

Sets a mag/min filter. 0 is linear, others are nearest.
This function will regenerate the texture. This means it shouldn't be
used in a loop.
https://learnopengl.com/img/getting-started/texture_filtering.png
left is nearest, right is linear.


## [fn Image.setData](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L131)

```
fn (i: ^Image) setData*(data: []uint32, dm: th.Vf2) {
```

Updates the image data. dm are the dimensions of the new image.
The new image doesn't have to be the same size as the old one.


## [fn Image.getData](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L145)

```
fn (i: ^Image) getData*(): []uint32 {
```

Gets the image data. This downloads the data from the GPU on **each call**.
Don't use in performance critical sections.


## [fn Image.makeRenderTarget](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L161)

```
fn (i: ^Image) makeRenderTarget*() {
```

Sets the image a the render target. This means stuff won't be drawn onto the
screen, but into the image. In this mode, the scaling is always 1. An the
resolution of the screen are the image's dimensions.


## [fn Image.removeRenderTarget](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/image.um#L170)

```
fn (i: ^Image) removeRenderTarget*(wp: th.Vf2) {
```

Returns to rendering onto the screen.
`wp`
: viewport to be set


