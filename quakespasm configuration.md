#Quakespasm configuration

##Download

http://quakespasm.sourceforge.net/download.htm

##Installation

###GOG

TODO0

###Steam

TODO0

###Retail

TODO1

##Command line

NOTE: You can run Quakespasm from any directory (confirmed on Windows, TODO0: test macOS and linux), but it will create a `history.txt` file in that directory, which will contain the history of the console commands you entered while playing, if any (TODO0 test mac and linux).

- Quake: `quakespasm -basedir <quake directory> -fitz`.
- Scourge of Armagon: `quakespasm -basedir <quake directory> -fitz -hipnotic`.
- Dissolution of Eternity: `quakespasm -basedir <quake directory> -fitz -rogue`.
- Malice: TODO1.
- Shrak: TODO1.
- Dimension of the Past: `quakespasm -basedir <quake directory> -fitz -game dopa`.

Use `-basedir` to specify where the directory with Quake data files is.
Use `-fitz` to play demos in main menu (like vanilla Quake).

##Dimension of the Past

Dimension of the Past (DOPA) is an "unofficial official" Episode 5 developed by MachineGames and released for free as a gift for the fans for Quake's 20th anniversary.

https://cdn.bethsoft.com/quake/dopa.rar

##Saves location

Savegames go into the `id1` directory in your Quake installation folder, eg. `C:\Games\Quake\id1`, or into the respective mission pack subdirectory (`C:\Games\Quake\hipnotic` or `C:\Games\Quake\rogue`)

##Controls settings

- Enable mouselook: `+mlook`.
- Enable crosshair: `crosshair 1`.
- Disable vertical auto-aim: `sv_aim 1`.

Faster rising underwater on RMB (add to your config):

    alias +movejump "+jump;+moveup;"
    alias -movejump "-jump;-moveup;"
    bind mouse2 +movejump

Source: https://www.quaddicted.com/quake/configuration

Switch weapons with mouse wheel:

    bind "mwheelup" "impulse 10"
    bind "mwheeldown" "impulse 12"

###Scourge of Armagon

Bind keys for new weapons:

    bind 9 "impulse 225"
    bind 0 "impulse 226"

Source: https://www.reddit.com/r/quake/comments/7y1msq/quake_scourge_of_armagon_new_gun_key_bindings/

##Graphics settings

- Disable texture filtering (causes blurry textures): `gl_texturemode GL_NEAREST_MIPMAP_NEAREST` or `GL_NEAREST`.
- Enable square particles (like vanilla Quake): `r_particles 2`.
- Disable animation interpolation (makes animations look choppy like in vanilla Quake): `r_lerpmodels 0` and `r_lerpmove 0`.
- Enable FSAA: `vid_fsaa 8`.

`gl_texturemode` values:
- `GL_NEAREST`: Point sampled (software-like). Lowest quality, highest performance.
- `GL_NEAREST_MIPMAP_NEAREST`: GL_NEAREST but with a bit more quality for far objects.
- `GL_NEAREST_MIPMAP_LINEAR`: GL_NEAREST but with even more quality for far objects.
- `GL_LINEAR`: No blending.
- `GL_LINEAR_MIPMAP_NEAREST`: Bilinear interpolation.
- `GL_LINEAR_MIPMAP_LINEAR`: Trilinear interpolation. Highest quality, lowest performance.

Source: https://www.quaddicted.com/webarchive/www.quaddicted.com/software-vs-glquake/software-vs-glquake-texture-filtering/

Bind filtering mode toggle to a key (add to your config):

    alias pixel_on "gl_texturemode GL_NEAREST; bind o pixel_off"
    alias pixel_off "gl_texturemode GL_LINEAR_MIPMAP_LINEAR; bind o pixel_on"
    bind o pixel_on

Source: https://www.quaddicted.com/webarchive/www.quaddicted.com/software-vs-glquake/software-vs-glquake-texture-filtering/

###Borderless window

Quakespasm supports `vid_borderless "1"` in config, but it doesn't seem to do anything (TODO1: Maybe try different fullscreen modes?).

##Multiplayer

TODO3

##Playing demos

Put the demo files into `id1` (or respective directory with `pak0.pak`), then
run Quakespasm the same way as when playing the game, but add
`+playdemo <demo name>` at the end. You can omit `-fitz` because it does nothing
when running with `+playdemo`.
For example, to play a demo of Scourge of Armagon, run this:

`quakespasm -basedir <quake directory> -hipnotic +playdemo <demo name>`

###dzip

TODO2: what's dzip and why care?

There seems to be no dz support in Quakespasm, so you'll have to extract it using dzip before playing.

####Downloads

Main page: http://speeddemosarchive.com/dzip/download.html
macOS: TODO2 (the version from the link above probably won't work on Catalina)
Alternate linux instructions: https://linuxg.net/install-dzip-on-ubuntu/


