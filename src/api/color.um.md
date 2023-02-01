## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/color.um#L0)

```
```

Color operations. Operate on RGBA uint32 values.


## [fn hsv](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/color.um#L11)

```
fn hsv*(h, s, v: th.fu, a: th.fu = 1.0): uint32 {
```

Converts HSV values into RGBA uint32 color.
NOTE: Hue is between 0 and 1


## [fn alpha](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/color.um#L18)

```
fn alpha*(c: uint32, to: th.fu): uint32 {
```

Sets alpha of the color c to a value in to.


## [fn rgb](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/color.um#L24)

```
fn rgb*(r, g, b: th.fu, a: th.fu = 1.0): uint32 {
```

Constructs RGBA uint32 from RGBA of reals.


