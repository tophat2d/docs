## [Window dimensions](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L14)

```
var (
	w*, h*: int32
)
```



## [Viewport size](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L19)

```
var wp*: th.Vf2
```



## [fn setViewport](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L29)

```
fn setViewport*(dm: th.Vf2) {
```

Sets the dimensions of the viewport. The dimensions are saved in the `wp`
variable.

`dm`
: dimension of the viewport


## [fn setup](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L40)

```
fn setup*(title: str = "tophat game", width: int = 400, height: int32 = 400) {
```

Sets up the engine and opens a window.


## [fn cycle](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L56)

```
fn cycle*(): bool {
```

Cycle needs to be called every cycle for the window to work. If the window
was closed, it returns false.


## [fn beginScissorRect](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L83)

```
fn beginScissorRect*(r: rect.Rect) {
```

Disable rendering outside of rect `r`


## [fn endScissor](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L89)

```
fn endScissor*() {
```

Stops cropping


## [fn setFullscreen](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L97)

```
fn setFullscreen*(fullscreen: bool) {
```

Makes window go full screen


## [fn isFullscreen](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L103)

```
fn isFullscreen*(): bool {
```

Returns true if window is fullscreen


## [fn getDims](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L109)

```
fn getDims*(): th.Vf2 {
```

Returns dimensions of the window in screen pixels.


## [fn setTargetFps](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L115)

```
fn setTargetFps*(fps: int) {
```

Sets the fps limit.

`fps`
: amount of fps the limit should be set to


## [fn setDims](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L125)

```
fn setDims*(dm: th.Vf2) {
```

Sets the dimensions of the window, linux only.

`dm`
: the target dimensions in screen pixels


## [fn setIcon](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L135)

```
fn setIcon*(img: image.Image) {
```

Sets the window icon, linux only.


## [fn showCursor](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L142)

```
fn showCursor*(show: bool) {
```

Show or hide the cursor, linux only.


## [fn freezeCursor](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/window.um#L149)

```
fn freezeCursor*(freeze: bool) {
```

Freezes the cursor in place. `input.getMouseDelta` will still report mouse
movements. Linux only.


