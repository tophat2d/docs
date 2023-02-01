## [struct Anim](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/anim.um#L5)

```
type Anim* = struct {
	// the source atlas
	atl: atlas.Atlas
	// the first cell of the animation
	min: int
	// the last cell of the animation
	max: int
	fps: real32
	// offset in time
	offset: int
}
```

Anim allows you to animate between individual frames of an atlas.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/anim.um#L19)

```
fn mk*(atl: atlas.Atlas, fps: int, min: int = 0, max: int = -1 /* len(atl) - 1 */, offset: int = -1 /* th.time */): Anim {
```

`Anim` constructor


## [fn Anim.animate](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/anim.um#L39)

```
fn (anm: ^Anim) animate*(time: int) {
```

Crops the base atlas to the cell that should be visible at `time`.


## [fn Anim.framesPlayed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/anim.um#L46)

```
fn (anm: ^Anim) framesPlayed*(time: int): int {
```

Returns how many frames were played at `time`.


