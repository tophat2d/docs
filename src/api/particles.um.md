## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/particles.um#L0)

```
```

Particles allow for *performant* and random particle systems.
TODO: a better constructor


## [struct Particle](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/particles.um#L8)

```
type Particle* = struct {
```

Particle struct. You can tweak the start_time for godot-like explossivness.


## [struct Emitter](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/particles.um#L15)

```
type Emitter* = struct {
	pos: th.Vf2 // position
	dm: th.Vf2 // size of the emittion area
	gravity: th.Vf2 // gravity
	repeat: bool // if false, particle won't be renewed
	active: bool // false, if there aren't any active particles anymore
	
	angle: th.Vf2 // angle in which particles are emitted

	lifetime: th.uu // lifetime of particles
	lifetimeRandomness: th.fu // randomness in %/100

	velocity: th.fu // velocity
	velocityRandomness: th.fu // randomness in %/100

	size: th.fu // size
	sizeRandomness: th.fu // randomness in %/100
	maxSize: th.fu // size at the end of particles lifetime

	rotation: th.fu
	rotationRandomness: th.fu
	maxRotation: th.fu

	colors: []uint32 // array of colors, which are interpolated between
	
	particles: []Particle // list of particles
}
```

Emitter. This is where everything is configured.


## [fn Emitter.draw](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/particles.um#L41)

```
fn (e: ^Emitter) draw*(cam: rect.Rect, t: int32) {
```

Draws and updates the particles.


