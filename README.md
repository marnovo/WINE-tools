# WINE tools, tips and tricks

WINE, Wineskin, Wineskin Winery (and related) tools, tips and tricks...
a.k.a. how to run Windows applications (kind of) natively in your macOS or Linux.

## What are these?

### WINE

What is [WINE](http://winehq.org/)? In short, "**W**INE **I**s **N**ot an **E**mulator".

### Wineskin

What is [Wineskin](https://sourceforge.net/projects/wineskin/)? In short, it is a standalone WINE wrapper.

### Wineskin Winery

What is [Wineskin Winery](http://wineskin.urgesoftware.com/tiki-index.php)? In short, it is a Wineskin (standalone WINE wrapper) generator.

_P.s.: keep in mind the original branch of the project development has been very infrequently updated._
_A recent fork with more active development can be found at [vitor251093/wineskin](https://github.com/vitor251093/wineskin)._

### Other options

PortingKit, WineBottler, GameOnMac, CrossOver, and eventually others.

[PortingTeam](http://portingteam.com/) and [PaulTheTall](https://www.paulthetall.com/) usually have ready-to-use wrappers for many games and applications.

## How to build a WINE engine from a compiled tarball

### Usage

You can use this to build OS X 10.8+ compatible 64bit engines that also work with 32bit apps. (Vanilla & Staging)
This is also a faster method to build 32bit Vanilla or Staging engines.

### Step-by-step guide

*Disclaimer: you may want to back things up before going ahead.*

1. Download the desired tarball at the [WINE builds website](https://dl.winehq.org/wine-builds/macosx/download.html). Do not unpack it.
2. Open terminal
3. Use the `cd` command to browse to the the folder where you put the Tarball (example: `cd Downloads/`)
4. Type in this command `tar xf XXXX.tar.gz` (replace XXXX with the name of the Tarball), this will extract a folder called `usr`
5. Type `touch version` to create an empty file without extension called `version`
6. Type `nano version`to open the nano text editor.
7. Type in the open file the name that you want to call your engine (example: `WS9Wine64bitStaging2.10-3`), save the file (Ctrl+O) and quit nano (Ctrl+X)
8. Put this file inside the `usr` folder that was created by extracting from the tarball previously
9. Type `mv usr/ wswine.bundle` to rename the `usr` folder as a `wswine.bundle` "file"
10. Type `tar cf - wswine.bundle | ~/Library/Application\ Support/Wineskin/7za a -si NAMEOFYOURENGINE.tar.7z` (Replace `NAMEOFYOURENGINE` with the name inside of the version file)
11. Move the newly created `.tar.7z` file inside `~/Library/Application Support/Wineskin/Engines`

Credits to [Brainzyy from PorkingKit](http://portingkit.com/smf/index.php?topic=290.0)
