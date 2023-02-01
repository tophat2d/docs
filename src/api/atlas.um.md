## [struct Atlas](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/atlas.um#L5)

```
type Atlas* = struct {
	i: image.Image // source image
	cs: th.Vf2 // size of a cell in pixels
	dm: th.Vf2 // amount of cells in image
}
```

Atlas is an image containing tiles in a square grid.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/atlas.um#L13)

```
fn mk*(i: image.Image, dm: th.Vf2): Atlas {
```

i: source image
dm: amount of cells


## [fn Atlas.coords](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/atlas.um#L24)

```
fn (a: ^Atlas) coords*(n: int): th.Vf2 {
```

returns the coordinates of the nth tile


## [fn Atlas.cropSource](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/atlas.um#L30)

```
fn (a: ^Atlas) cropSource*(at: th.Vf2) {
```

Crops the sourse image to only show a wanted tile


## [fn Atlas.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/atlas.um#L41)

```
fn (a: ^Atlas) draw*(at: th.Vf2, t: th.Transform) {
```

Draws the tile at `at`


