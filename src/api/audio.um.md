## [](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L0)

```
```

Module for audio loading and playback.


## [opaque Sound](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L3)

```
type Sound* = struct { _: ^struct{} }
```

Represents an instance of a playable sound. It is an opaque structure.


## [fn load](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L9)

```
fn load*(path: str): Sound {
```

Loads a sounds at path, if there is an error, the underlying pointer
will be `NULL` and `validate` will return false.


## [fn Sound.copy](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L17)

```
fn (s: ^Sound) copy*(): Sound {
```

Copies the sound. This will create another sound which can be configured
and played independently from the original sound.


## [fn Sound.validate](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L24)

```
fn (s: ^Sound) validate*(): bool {
```

Returns `true` if `s` loaded correctly.


## [fn Sound.isPlaying](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L31)

```
fn (s: ^Sound) isPlaying*(): bool {
```

Returns true if the sound is still playing.


## [fn Sound.play](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L38)

```
fn (s: ^Sound) play*() {
```

Plays the sound.


## [fn Sound.start](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L44)

```
fn (s: ^Sound) start*(): ^Sound {
```

The start function allows you to play a single sound multiple times.
It will create a copy and return a pointer to it, so you can controll it
while it is playing. The returned pointer can be discarded.


## [fn Sound.stop](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L57)

```
fn (s: ^Sound) stop*() {
```

Stops the sound, but keeps the progress. If you want to start from the
begginning, use `audio.Sound.seekToFrame(0)`.


## [fn Sound.setVol](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L65)

```
fn (s: ^Sound) setVol*(vol: real32) {
```

Sets the volume as a multiplier of the base volume.


## [fn Sound.setPan](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L72)

```
fn (s: ^Sound) setPan*(pan: real32) {
```

Sets the pan of the sound.


## [fn Sound.setPitch](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L79)

```
fn (s: ^Sound) setPitch*(pitch: real32) {
```

Sets the pitch of the sound.


## [fn Sound.setLooping](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L86)

```
fn (s: ^Sound) setLooping*(looping: bool) {
```

Sets whether the sound will loop upon finishing.


## [fn Sound.seekToFrame](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L93)

```
fn (s: ^Sound) seekToFrame*(frame: uint) {
```

Seeks to a specified PCM frame.


## [fn Sound.frameCount](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L100)

```
fn (s: ^Sound) frameCount*(): uint {
```

Returns length of the sound in PCM frames.


## [fn Sound.setStartTimeMs](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L107)

```
fn (s: ^Sound) setStartTimeMs*(t: uint) {
```



## [fn Sound.setStopTimeMs](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/audio.um#L113)

```
fn (s: ^Sound) setStopTimeMs*(t: uint) {
```



