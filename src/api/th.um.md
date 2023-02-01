## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L0)

```
```

Module with useful variables and types.
Variables: time, delta, platform
Constants: black, white, red, green, blue, yellow, magenta, cyan.


## [Tophat type aliases](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L8)

```
type fu* = real32
// standard type for integer values
type iu* = int32
// standard type for unsigned values
type uu* = uint32
```

standard type for real values


## [struct Vf2](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L16)

```
type Vf2* = struct {
	x, y: fu
}
```

vector 2


## [fn mkVf2](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L22)

```
fn mkVf2*(x: fu = 0, y: fu = 0): Vf2 {
	return Vf2{x, y}
}
```

Vf2 constructor


## [fn Vf2.rotated](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L28)

```
fn (p: ^Vf2) rotated*(origin: Vf2, rot: fu): Vf2 {
```

rotates `p` around `origin` with `rot` in degrees


## [fn Vf2.distanceTo](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L42)

```
fn (p1: ^Vf2) distanceTo*(p2: Vf2): fu {
```

distance between p1 and p2


## [fn Vf2.angleTo](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L48)

```
fn (p1: ^Vf2) angleTo*(p2: Vf2): real {
```

Angle between p1 and p2


## [fn Vf2.abs](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L55)

```
fn (p: ^Vf2) abs*(): Vf2 {
```

Absolute value of a vector.


## [fn Vf2.round](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L61)

```
fn (p: ^Vf2) round*(): Vf2 {
```

Rounds a vector.


## [fn Vf2.trunc](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L67)

```
fn (p: ^Vf2) trunc*(): Vf2 {
```

Truncates a vector.


## [fn Vf2.floor](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L73)

```
fn (p: ^Vf2) floor*(): Vf2 {
```

Floors a vector.


## [fn Vf2.ceil](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L79)

```
fn (p: ^Vf2) ceil*(): Vf2 {
```

Ceils a vector.


## [fn vf2f](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L85)

```
fn vf2f*(f: fu): Vf2 {
```

Creates a vector with both x and y set to f


## [fn Vf2.sub](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L91)

```
fn (p: ^Vf2) sub*(p2: Vf2): Vf2 {
```

Subtracts a vector from another one.


## [fn Vf2.subf](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L97)

```
fn (p: ^Vf2) subf*(f: fu): Vf2 {
```

Subtracts a fu from a vector.


## [fn Vf2.add](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L103)

```
fn (p: ^Vf2) add*(p2: Vf2): Vf2 {
```

Adds a vector to another one.


## [fn Vf2.addf](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L109)

```
fn (p: ^Vf2) addf*(f: fu): Vf2 {
```

Adds a fu to a vector.


## [fn Vf2.div](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L115)

```
fn (p: ^Vf2) div*(p2: Vf2): Vf2 {
```

Divides a vector by another one.


## [fn Vf2.divf](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L121)

```
fn (p: ^Vf2) divf*(f: fu): Vf2 {
```

Divides a vector by a fu.


## [fn Vf2.mul](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L127)

```
fn (p: ^Vf2) mul*(p2: Vf2): Vf2 {
```

Multiplies a vector by another one.


## [fn Vf2.mulf](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L133)

```
fn (p: ^Vf2) mulf*(f: fu): Vf2 {
```

Multiplies a vector by a fu.


## [fn Vf2.mag](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L139)

```
fn (p: ^Vf2) mag*(): fu {
```

Returns the magnitude of a vector p.


## [fn Vf2.norm](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L145)

```
fn (p: ^Vf2) norm*(): Vf2 {
```

Normalizes a vector.


## [fn Vf2.dot](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L154)

```
fn (p: ^Vf2) dot*(q: Vf2): fu {
```

Calculates dot product between 2 vectors.


## [struct Transform](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L160)

```
type Transform* = struct {
	p: Vf2 // position
	s: Vf2 // scale
	o: Vf2 // origin
	r: fu  // rotation
}
```

Struct defining transformation. Used for example by entities.


## [fn mkTransform](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L169)

```
fn mkTransform*(p: Vf2, s: Vf2 = Vf2{1, 1}, o: Vf2 = Vf2{0, 0}, r: fu = 0.0): Transform {
```

Transform constructor


## [fn Transform.transformed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L176)

```
fn (o: ^Transform) transformed*(t: Transform): Transform {
```

Transforms a transform with another transform.


## [fn Vf2.transformed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L185)

```
fn (v: ^Vf2) transformed*(t: Transform): Vf2 {
```

Transforms a vf2 to another vf2.
Order:
1. scale
2. rotation
3. position

This allows conversion from a relative to an absolute vf2.


## [type Quad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L199)

```
type Quad* = [4]Vf2
```



## [fn Quad.transformed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L203)

```
fn (q: ^Quad) transformed*(t: Transform): Quad {
```

Transforms a quad into another quad.
Order:
1. scale
2. rotation
3. position


## [fn getGlobal](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L216)

```
fn getGlobal*(): ^struct{} {
```

returns a pointer to the th_global. Set this as your extensions thg.


## [fn getFuncs](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L223)

```
fn getFuncs*(): ^struct{} {
```

returns pointer to tophat functions. Pass this to th_ext_set.


## [Color constants](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L229)

```
const (
	black* = 0xff
	white* = 0xffffffff
	red* = 0xff0000ff
	green* = 0x00ff00ff
	blue* = 0x0000ffff
	yellow* = 0xffff00ff
	magenta* = 0xff00ffff
	cyan* = 0x00ffffff
)
```



## [Misc variables](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/th.um#L241)

```
var (
	// time in ms from start of the game
	time*: uint
	// length of the last frame in ms
	delta*: int
	// platform tophat is running on
	platform*: str = "linux"
)
```



