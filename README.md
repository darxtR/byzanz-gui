# byzanz-gui

Lightweight front end for byzanz (GIF screen recorder) with three area selections modes (full screen, window and region), optional popup input prompts (duration/delay) and notifications issued both when the application starts and stops to record.

Written in bash with minimal systems and hot keys in mind and depends only on tools widely available through distribution repositories. Namely `byzanz`, `xwininfo` (window mode), `xdotool` (region mode), `zenity` (prompts) and `notify-send` (notifications), most of which, apart from byzanz, usually comes pre-installed with systems running Xorg.

## Installing

Make the file executable and install it to a folder in your PATH, like `$HOME/.local/bin` or `/usr/local/bin` to run it anywhere from your command line anywhere, or simply run the file directly using `bash byzanz-gui`.

## Running

### Modes

Apart from the default full screen mode provided by byzanz this script provides two more modes.

#### window

`byzanz-gui -m window`

After being prompted for duration(s), select the window you want to record.

You will know when to select the window to record as the mouse pointer then takes the shape of a plus sign, '+'.

#### Region (Rectangular free-hand)

`byzanz-gui -m region`

After being prompted for duration(s), click two times on the screen. Everything between these points will be recorded.

You will know when to select the region to record as the mouse pointer then takes the shape of a plus sign, '+', up until the second point has been chosen.

### Other

    [user@host ~]$ byzanz-gui --help

    usage: byzanz-gui [-t <dir>] [-e <byzanz|flv|gif|ogg|ogv|webm>] [-p <path>]

    Options inherited directly from byzanz-record:
      -a, --audio               Record audio.
      -c, --cursor              Record cursor.
      -d, --duration            Predefined duration. Disables input request dialog.
          --delay               Predefined delay. Disables input request dialog.
      -x, --x=PIXEL             Predefined region, X. Upper most left, as pixels.
      -y, --y=PIXEL             Predefined region, Y. Upper most left, as pixels.
      -w, --width=PIXEL         Predefined region, width as pixels.
      -h, --height=PIXEL        Predefined region, height as pixels.

    Application options
      -b, --byzanz-record=PATH  Path to byzanz executable, or name found in $PATH.
          --default-delay       Default delay. Displayed in dialogs.
          --default-duration    Default duration. Displayed in dialogs.
          --default-directory   Default directory. Displayed in dialogs.
          --date-fmt=FMT        Use this time format to generate the filename.
      -e, --file-ext=EXT        Default and temporary file extension. Defaults to
                               flv when audio is being recorded, otherwise gif.
          --file-fmt=NAME     File name format (default=)
      -f, --frame             Do not ignore frame during quick window select.
      -m, --select-mode=MODE  Predefine mode. Can by any of none, region and window.
      -n, --no-countdown      Disable notify-send countdown.
      -i, --invisible         Disable visual notifications (notify-send).
      -p, --path=PATH         Save to PATH (disables the file selection prompt).
      -q, --quiet             Use default values. Supress all input dialogs.
      -s, --silent            Supress sounds. This can also be achieved gloabally
                             with 'export BYZANZ_GUI_SILENT=true'.
      -t, --temp-dir=DIR   Temporary directory.

      -h, --help              Show this help message.
      -u, --usage             Show usage string.

    EXT
        byzanz
        flv
        gif
        ogg
        ogv

    MODE
        none        Record full screen.
        window      Quick select region by clicking a X window.
        region      Quick select a custm region with two mouse clicks.

    NAME
        %%PID%%     Replaced with PID of byzanz-gui.
        %%DATE%%    Replaced with date of byzanz-gui execution.


    All other arguments is passed onto byzanz.
    
    * Please take note of the -p/--path and -m/--mode options. *
