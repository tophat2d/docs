# Playing sounds

All of the sound stuff is in the [audio.um](/api/audio.um.md). First step is
loading a sound from a file.

```
mySound := audio.load("sfx/music.mp3")
```

Supported formats are mp3, flac and wave. You can modify some properties of
the sound.

```
mySound.setLooping(true)
mySound.setVol(0.5)
```

If you want to play it, use the play method.

```
mySound.play()
```

Keep in mind that you can't play a sound multiple times at once.  A solution to
this is to make copies of a sound using the `copy` method.

```
mySound.copy().play()
```

```
import (
	"audio.um"
	"th.um"
	"window.um"
)

fn init*() {
	window.setup()

	mySound := audio.load("sfx/music.mp3")
	mySound.setLooping(true)
	mySound.setVol(0.5)
	mySound.play()
}
```
