# byzanz-gui
Light weight front end for byzanz (GIF screen recorder) with window and rectanglular selection, written in bash for minimal systems and hot keys in mind.

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
      -i, --invisible         Disable all notifications sent with notify-send.
      -p, --path=PATH         Write directly to PATH and disable file selection.
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

    * Please take note of the -p/--path option. *
