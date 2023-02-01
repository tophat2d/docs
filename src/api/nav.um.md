## [struct Mesh](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/nav.um#L6)

```
type Mesh* = struct {
	// The mesh data.
	d: []bool
	// The dimensions and position of the mesh, r.w == w * s
	r: rect.Rect
	// Width of the mesh.  Used to adress the mesh data.
	w: th.uu
	// Scale of one cell (cell is a square)
	s: th.fu
}
```

Mesh is a 2d array of bool cells.  If a cell is true, the cell can be used
in a path.  The mesh is located in a world using the `r` field.  A cell can
have an arbitrary size as specified by `s`.

The mesh can be edited using the `addQuad` method, but it should be trivial
to add your own, similar methods.

Please use the `mk` constructor to construct a `Mesh`, unless you really
know what you're doing.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/nav.um#L27)

```
fn mk*(r: rect.Rect, s: th.fu): Mesh {
```

Creates a new nav mesh. The dimensions must be divisible by the scale.
`r`
: the rectangle of the mask
's'
: the scale of the mask


## [fn Mesh.addQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/nav.um#L49)

```
fn (m: ^Mesh) addQuad*(q: th.Quad) {
```

Sets mask's fields overlapping `q` to `false`.


## [fn Mesh.nav](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/nav.um#L56)

```
fn (m: ^Mesh) nav*(p1, p2: th.Vf2): []th.Vf2 {
```

Navigates between `p1` and `p2`. Returns the path as an array of `th.Vf2`s.
If it doesn't find any path, or one of the points is outside of the mask,
returns an empty array.


