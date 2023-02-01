## [struct Ent](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L6)

```
type Ent* = struct {
	// used as a collider, used as backup when invalid image is supplied
	r: rect.Rect
	// used in drawing
	i: image.Image
	// used to transform and translate the image and rect
	t: th.Transform
	// used as a color of the rect and a color filter for the image
	c: uint32
}
```

Entity is the main game object. It features drawing and collisions.
Every entity has an image used for drawing and a rectangle used
for collisions. It also has a transform used for transforming it's image
and rectangle.


## [struct Coll](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L22)

```
type Coll* = struct {
	index: th.uu
	pos: th.Vf2
}
```

Value returned by get coll. It contains a position where the collision
happened and the index of the entity involved in said collision.


## [fn Ent.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L31)

```
fn (e: ^Ent) draw*(c: rect.Rect) {
```

Draws the entity onto the screen in relaction to camera c.


## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L37)

```
fn mk*(img: image.Image = image.Image{}, t: th.Transform = th.Transform{ s: th.Vf2{1, 1} }): Ent {
```

ent's constructor


## [fn Ent.getColl](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L57)

```
fn (e: ^Ent) getColl*(s: []^Ent, maxColls: th.uu): []Coll {
```

Checks collisions of e with entities in s. Checks at max maxColl collisions.
If s contains e, the collision won't be returned.


## [fn Ent.animate](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/ent.um#L76)

```
fn (e: ^Ent) animate*(fps: int, frames: ^[]image.Image, t: int) {
```

Animates the entity's image with one of the `anim` array. <b>Won't</b> begin on
the first frame. If you want that, use anim.Anim.


