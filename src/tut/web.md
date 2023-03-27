# Making web builds

Tophat games can be exported to run on the web.

## Linux

On Linux you can use the
[`th_emscripten_link`](https://tophat2d.dev/dl/th_emscripten_link) script.  When
passed files, the script will make a web build of your game and save it to the
`wasm-out` directory.  Example:

> Before using the script, you need to install emscripten. On Ubuntu, you can
> do that using `apt install emscripten`.

```
$ ls
main.um image_the_game_needs.png another_resource.txt
$ th_emscripten_link main.um image_the_game_needs.png another_resource.txt
$ ls
main.um image_the_game_needs.png another_resource.txt wasm-out
```

If you run the script for the first time, it will download some resources from
the internet.  The script can take some time to run.  After it finished, the
result is in the `wasm-out` directory.

## Windows

Making web builds on windows isn't done yet (To: ~ske)
