<p align="center"><img src="extra/kunst_logo.png"><br><sub>✨ Download and display album art or display embedded album art  ✨</sub></p>

```kunst``` is a daemon that extracts the album art from the songs playing in ```mpd``` and displays them in the a little window. It doesn't loop on a timer, instead it waits for ```mpd``` to send a ```player``` event. When it receives a ```player``` event, it wakes up and extracts the album art of the current playing track. This makes ```kunst```really lightweight and makes it idle at ```~0%``` CPU usage. If there no embbeded album art, it will try to fetch the album art from the internet.


<p align="left">
<img src="extra/demo.gif">
</a>
</p>

## Dependencies
- ```sxiv```
- ```bash```
- ```ffmpeg```
- ```mpc```
- ```jq```
- ```mpd```


## Usage

```bash
$ kunst --help
usage: kunst [-h|--help] [--size "px"] [--position "+x+y"]
             [--music_dir "path/to/dir"] [--verbose] [--silent] [--version]

┬┌─┬ ┬┌┐┌┌─┐┌┬┐
├┴┐│ ││││└─┐ │
┴ ┴└─┘┘└┘└─┘ ┴
Download and display album art or display embedded album art

optional arguments:
   -h, --help            show this help message and exit
   --size                what size to display the album art in
   --position            the position where the album art should be displayed
   --music_dir           the music directory which MPD plays from
   --verbose             show the output
   --force-online        force getting cover from the internet
   --version             show the version of kunst you are using
   --silent              update cover, but dont display with nsxiv
   --custom-fallback     path to custom fallback, used instead of music note
```


## Configure
You can configure `kunst` through environment variables.

```bash
# The size of the album art to be displayed
export KUNST_SIZE="250x250"

# The position where the album art should be displayed
export KUNST_POSITION="+0+0"

# Where your music is located
export KUNST_MUSIC_DIR="/home/username/Music/"
```


## License
MIT License

Copyright © 2019 Siddharth Dushantha
