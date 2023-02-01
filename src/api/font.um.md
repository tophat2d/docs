## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L0)

```
```

Module for font rendering. Unicode is supported, but only left to right.


## [Filtering constants](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L6)

```
const (
	filterBilinear* = 0
	filterNearest* = 1
)
```



## [opaque Font](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L12)

```
type Font* = struct { _: ^struct{} }
```



## [fn load](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L17)

```
fn load*(path: str, size: th.fu, filter: uint32 = filterBilinear): Font {
```



## [fn Font.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L23)

```
fn (f: ^Font) draw*(text: str, pos: th.Vf2, color: uint32, scale: th.fu = 1.0) {
```



## [fn Font.validate](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L28)

```
fn (f: ^Font) validate*(): bool {
```



## [fn Font.measure](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/font.um#L34)

```
fn (f: ^Font) measure*(text: str): th.Vf2 {
```



