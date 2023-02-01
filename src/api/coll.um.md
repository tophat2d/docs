## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L0)

```
```

Builtin collision functions. The ic argument stores the collision position.


## [fn lineToLine](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L8)

```
fn lineToLine*(b1, e1, b2, e2: th.Vf2, ic: ^th.Vf2): bool {
```

Checks for a collision between 2 lines specified by their end points.


## [fn vf2ToQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L15)

```
fn vf2ToQuad*(p: th.Vf2, q: th.Quad, ic: ^th.Vf2): bool {
```

Checks for a collision between a vf2 and a quad.


## [fn lineToQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L22)

```
fn lineToQuad*(b, e: th.Vf2, q: th.Quad, ic: ^th.Vf2): bool {
```

Check for a collision between a line and quad edges.


## [fn quadToQuad](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L29)

```
fn quadToQuad*(q1, q2: th.Quad, ic: ^th.Vf2): bool {
```

Check for a collision between two quads.


## [fn vf2ToRect](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L36)

```
fn vf2ToRect*(p: th.Vf2, r: rect.Rect): bool {
```

Check for a collision between a vf2 and a rectangle.


## [fn rectToRect](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/coll.um#L43)

```
fn rectToRect*(r1, r2: rect.Rect): bool {
```

Check for a collision between two rects


