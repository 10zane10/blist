# blist

A simple shell script to conveniently play music and playlists from the
command line in mplayer. Blist is expected to never excede 500 lines of code.

## Installation

1. Install mplayer
2. Copy files into a directory in $PATH

```sh
$ sudo cp blist* /usr/local/bin
```

3. Copy config to ~/.config/blist

```sh
$ mkdir -p ~/.config/blist
$ cp config ~/.config/blist
```

## Usage

### Starting out

To run blist (without giving it a playlist) type `$ blist`

This will print a list of songs in your ~/Music folder and will give you an
interactive menu to play the songs. Once you search for the song you want to
start at, it will open the songs in mplayer starting at that song. 

### The playlist and song directories

The playlist and song directories are where blist searches for songs and
playlist respectedly. These are set by PLAYLISTDIR and MUSICDIR (found in
~/.config/blist/config). The music directory is typically ~/Music while the
playlist directory is typically ~/Music/playlists.  

 - To list all playlists in the playlist directory run `$ blistdb -p`.
 - To list all songs in the song directory run `$ blistdb -m`.

### Playlists

blist playlist is simply a file containing a list of the songs you want to play.

Assuming the following is in the file `playlist` located somewhere in the
playlist directory...

```
all-star.mp3
fat-rat-unity.wav
bohemian-rhaps
```

`$ blist playlist` will play all-star.mp3 fat-rat-unity.wav and
bohemian-rhapsody.flac (assuming you have these files in the song directory

The names do not have to be the complete /path/to/file nor do they even need to
be the complete file name. In fact, including the path may cause the file to be
skipped in some cases.
