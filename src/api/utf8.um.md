## [type Rune](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L1)

```
type Rune* = int32
```



## [fn Rune.size](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L4)

```
fn (r: ^Rune) size*(): int {
```



## [fn Rune.encode](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L21)

```
fn (r: ^Rune) encode*(): str {
```



## [fn getNextRune](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L43)

```
fn getNextRune*(a: str, pos: int): Rune {
```



## [fn decode](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L48)

```
fn decode*(s: str): []Rune {
```



## [fn realLength](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/utf8.um#L61)

```
fn realLength*(s: str): int {
```



