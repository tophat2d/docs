## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L0)

```
```

A module for importless communication between modules. A signal is a set of
callbacks.  You can use signals directly in your own structs if you want
them to be instance specific, of you can use global signals which are
adressed by a string name.


## [type Callback](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L6)

```
type Callback* = fn(cctx, uctx: any) 
```

`cctx` is value passed by the caller to `emit`. `uctx` is the value passed
to the register function.


## [type Id](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L15)

```
type Id* = uint
```



## [type Signal](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L18)

```
type Signal* = map[Id]User
```



## [fn mk](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L23)

```
fn mk*(): Signal {
```

`Signal` constructor


## [fn Signal.register](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L29)

```
fn (this: ^Signal) register*(callback: Callback, uctx: any): Id {
```

Registers a callback to a signal and returns the callback id.


## [fn Signal.remove](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L37)

```
fn (this: ^Signal) remove*(id: Id) {
```

Removes a callback by id.


## [fn Signal.emit](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L43)

```
fn (this: ^Signal) emit*(ctx: any) {
```

Emits a signal.


## [fn register](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L51)

```
fn register*(name: str, callback: Callback, uctx: any): Id {
```

Registers a callback to a global signal.  There is no need to explicitely
create global signals.  Returns id of the added callback


## [fn remove](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L61)

```
fn remove*(name: str, id: Id) {
```

Removes a callback from a global signal by id.


## [fn emit](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/signal.um#L67)

```
fn emit*(name: str, ctx: any) {
```

Calls all callbacks associated with the passed global signal name.


