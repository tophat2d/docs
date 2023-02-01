# Installation

The first step on the road to using tophat is to install it.  If you download
the prebuilt binaries, it is a very simple process.

## Installing tophat on Linux

> All commands are prefixed either using `$` or `#`.  The former is used for
> commands that can be run as a normal user, latter is used for commands
> requiring root privileges.

First you have to download tophat from [this page](https://th.mrms.cz/dl).  You
can do that manually or using this `curl` command.

```sh
$ curl https://th.mrms.cz/dl/tophat-linux -o tophat
```

When you successfully download the binary, the next step is to install it to a
directory, which is in the system path.  For example `/usr/bin`.

```
# install tophat /usr/bin
```

To check if tophat was installed correctly, run `tophat version`.

## Installing tophat on Windows

Download the tophat exe from the [downloads page](https://th.mrms.cz/dl).  Then
move it to a folder of your liking.  Whenever you want to make a tophat
project, it is recommended to make a shortcut to tophat in the project
directory. This way you won't have to use the file dialog every time you run
your game.

## Running the examples

To run the examples, clone the [tophat repository](https://sr.ht/~mrms/tophat).
The examples are in the `examples/` folder.  On linux, cd to an example you
want to run and type `tophat`.  On windows, launch tophat and choose the folder
of the example you want to run.

## Text editors with umka support

No text editors support umka out-of-the-box, but there are available extensions
for the most popular ones.

* [VS code](https://marketplace.visualstudio.com/items?itemName=mrms.vscode-umka)
* [VIM](https://git.sr.ht/~mrms/vim-umka)
* [nano](https://mrms.cz/dl/up/umka.nanorc)
* [sublime text](https://github.com/vtereshkov/umka-lang/blob/master/Umka.sublime-syntax)
