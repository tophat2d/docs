## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L0)

```
```

Tilemaps allow for easy level construction and fast collisions. You can even
use them for some games instead of entities (tetris comes to mind)


## [Direction constants used for autotile](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L10)

```
const (
	top* = 1
	right* = 2
	bot* = 4
	left* = 8
)
```



## [struct Tilemap](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L18)

```
type Tilemap* = struct {
	atlas: atlas.Atlas
	pos: th.Vf2
	w: th.uu // width of tilemap
	cells: []th.uu // all cells (this will draw the tile in tiles with number in cells - 1)
	collMask: []bool // if true, the tile collides
	scale: th.fu
}
```

Tilemap struct


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L29)

```
fn mk*(cells: []th.uu, w: th.uu, at: atlas.Atlas, scale: th.fu = 1): Tilemap {
```



## [fn Tilemap.edit](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L41)

```
fn (t: ^Tilemap) edit*(x, y, tile: int) {
```

Sets tile at [x, y] to tile.


## [fn Tilemap.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L48)

```
fn (t: ^Tilemap) draw*(cam: rect.Rect) {
```

Draws the tilemap.


## [fn Tilemap.getColl](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L56)

```
fn (t: ^Tilemap) getColl*(e: ent.Ent, vert: ^th.uu, pos: ^th.Vf2): bool {
```

Checks, if t collides with e.
pos is the tile index where the collision happened
vert is which index collided
You need to pass a valid pointer (TODO)


## [fn Tilemap.autotile](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/tilemap.um#L68)

```
fn (t: ^Tilemap) autotile*(src, tileCfg: []th.uu, tile: th.uu) {
```

Autotile turns all `tile` tiles in `src` into tiles in `tileCfg`, so they
follow up correctly. `tileCfg` is an array of 16 tiles. They are placed in
a way where OR of all the places where the tile continues (top, right bot,
right). The constants for them are defined in this file. Example:
tileCfg[top | bot] = 21
top | bot would look something like this: |


