# blist

A simple shell script to conveniently play music and playlists from the command
line (with mplayer). Blist is never expected to exceed 500 lines of code.

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

To run blist (without giving it a playlist) run `$ blist` in your terminal.

This will print a list of songs in your ~/Music folder and will give you an
interactive menu to play the songs. Once you search for a song you want to
start at or press enter, it will run the songs in mplayer.

### The playlist and song directories

The playlist and song directories are where blist searches for songs and
playlist respectively. These are set by PLAYLISTDIR and MUSICDIR (found in
~/.config/blist/config). The music directory is typically ~/Music while the
playlist directory is typically ~/Music/playlists.  

 - To list all playlists in the playlist directory run `$ blistdb -p`.
 - To list all songs in the song directory run `$ blistdb -m`.

### Playlists

A blist playlist is simply a file containing a list of the songs you want to
play. The names do not have to be the complete /path/to/file nor do they even
need to be the complete file name. 

If music direcotry contains files:

```
all-star.mp3
bohemian-rhapsody.flac
instanbul.wav
fat-rat-unity.wav
other-song.mp3
```

And there is a file named 'playlist' located somewhere in the playlist
directory:

```
all-star.mp3
fat-rat-unity.wav
bohemian-rhaps
```

Then `$ blist playlist` will play all-star.mp3, fat-rat-unity.wav, and
bohemian-rhapsody.flac.

Note: You do not need to be in the same directory as the playlist to use the
playlist.
