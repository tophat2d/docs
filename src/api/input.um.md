## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L0)

```
```

Module for getting keyboard and mouse input.
is* functions return info based on a us QWERTY layout. They are supposed to
be used for game controls. For text input use getStr.


## [Keycode constants](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L9)

```
const (
	mouse1* =        char(1)
	mouse2* =        char(2)
	mouse3* =        char(3)
	mouse_up* =      char(4)
	mouse_down* =    char(5)
	key_shift* =     char(16   + 0x7f)
	key_backspace* = char(8    + 0x7f)
	key_delete* =    char(46   + 0x7f)
	key_left* =      char(37   + 0x7f)
	key_right* =     char(39   + 0x7f)
	key_up* =        char(38   + 0x7f)
	key_down* =      char(40   + 0x7f)
	key_escape* =    char(27   + 0x7f)
	key_enter* =     char(13   + 0x7f)	
	key_alt* =       char(0x12 + 0x7f)
	key_ctrl* =      char(0x11 + 0x7f)
	key_tab* =       char(0x09 + 0x7f)
	key_pg_down* =   char(0x22 + 0x7f)
	key_pg_up* =     char(0x21 + 0x7f)
	key_home* =      char(0x24 + 0x7f)
	key_end* =       char(0x23 + 0x7f)
	key_insert* =    char(0x2d + 0x7f)
	// F1 = key_fn+1, F2 = key_fn+2 etc.
	key_fn* =        char(0x70 - 1)
)
```



## [fn getMousePos](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L38)

```
fn getMousePos*(): th.Vf2 {
```

Returns the position of mouse cursor in relation to the screen.


## [fn getGlobalMousePos](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L46)

```
fn getGlobalMousePos*(cam: rect.Rect): th.Vf2 {
```

Returns the position of mouse cursor in relation to cam.


## [fn isPressed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L53)

```
fn isPressed*(code: char): bool {
```

Returns true if key is pressed. Either use codes defined in the file above,
or pass lower case char/number.


## [fn isJustPressed](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L62)

```
fn isJustPressed*(code: char): bool {
```

Returns, whether code was just pressed this loop.


## [fn isJustReleased](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L69)

```
fn isJustReleased*(code: char): bool {
```

Returns true if a key was just released.


## [fn clear](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L76)

```
fn clear*(code: char) {
```

Clears both the pressed and justPressed state of a code.


## [fn getStr](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L83)

```
fn getStr*(): str {
```

Returns a string entered by the user in the last cycle.


## [fn getMousDelta](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/input.um#L90)

```
fn getMouseDelta*(): th.Vf2 {
```

Returns the difference between mouse positions in the last cycle. Will work
even if `window.freezeCursor` is enabled.


