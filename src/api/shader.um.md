## [opaque Shader](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L4)

```
type Shader* = struct {
```

Shader allows you to define your own vertex and fragment GLSL shaders. This
is a low-level feature, so it's very easy to mess up.

In tophat, instead of a main function, shaders provide th_vertex and
th_fragment. The signature of th_vertex is:

```
vec2 th_vertex(vec2 vert);
```

where vert is the position of the vertex taken from the vertex buffer.
The output is the vertex shader output.

As for fragment shaders, there are two types of them. One for canvas
and one for images. In canvas shaders, the fragment function is very simple:

```
vec4 th_fragment(vec4 color);
```

Image fragment function looks like this:

```
vec4 th_fragment(sampler2D tex, vec2 coord);
```

where tex is the texture and coord are the texture coordinates. Be aware to
swap the output of the `texture2D` function. Example:

```
texture2D(tex, coord).abgr
```


## [Default shader constants](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L42)

```
const (
	defaultImageShader* = Shader{1}
	defaultCanvasShader* = Shader{2}
)
```



## [struct Uniform](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L48)

```
type Uniform* = struct {
	s: Shader
	l: uint
}
```

Represents a GLSL uniform.


## [fn mkCanvas](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L56)

```
fn mkCanvas*(vertex, fragment: str): Shader {
```

Compiles a canvas shader from source. If there is a compilation error, it
will print something to the console.


## [fn mkImage](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L64)

```
fn mkImage*(vertex, fragment: str): Shader {
```

Compiles an image shader from source. If there is a compilation error, it
will print something to the console.


## [fn Shader.pickForCanvas](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L72)

```
fn (s: ^Shader) pickForCanvas*() {
```

Picks the shader to be used for canvas drawing. Flushes the canvas batch.


## [fn Shader.pickForImage](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L79)

```
fn (s: ^Shader) pickForImage*() {
```

Picks the shader to be used for image drawing. Flushes the image batch.


## [fn Shader.getUniformLocation](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L86)

```
fn (s: ^Shader) getUniformLocation*(name: str): Uniform {
```

Retunrs a uniform by name.


## [fn Uniform.setInt](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L93)

```
fn (u: ^Uniform) setInt*(value: int) {
```

Sets a uniform to an int value. Flushes both batches.


## [fn Uniform.setVf2](https://git.sr.ht/~mrms/tophat/tree/main/item/umka/shader.um#L100)

```
fn (u: ^Uniform) setVf2*(value: th.Vf2) {
```

Sets a uniform to a vf2. Flushes both batches.


