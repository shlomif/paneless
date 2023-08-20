# NAME

	paneless - multipane pager

![GUI](https://github.com/nkh/paneless/blob/main/media/paneless.png)

# SYNOPSIS

	paneless [-t -a -l -L] file <(seq 5) file ...

# DESCRIPTION

***paneless*** reads its input stream from its arguments (no piping), formats them to fit the terminal, and colors them. Processing multiple large inputs may take time to process, and so does input that contains ANSI color codes.

Once processed vertical scrolling is fast; horizontal scrolling re-processes all the inputs.

I also use paneless as a frontend for https://github.com/nkh/tdiff and https://github.com/nkh/tcol via a simple API which you might find convenient.

## ANSI

*paneless* will display files that contain ANSI codes, if you use the *--ansi* option. You will need to install *ansiexpand* for proper tab expansion.

## Options

| short      | long          | function                                         |
| ---------- | ------------- | ------------------------------------------------ |
| -a         | --ansi        | input contains ANSI color codes                  |
| -c file    | --custom=file | add custom commands                              |
| -C column  |               | column has custom renderer                       |
| -e="k=v"   |               | store option for custom commands                 |
| -I         |               | custom initial content                           |
| -l         | --line-number | overlay the top line number                      |
| -L         |               | overlay the bottom line number                   |
|            | --no-bindings | 'quit' bindings only                             |
|            | --no-color    | do not color text                                |
|            | --status-line | reserve space for status line                    |
| -t=tabsize |               | set tab size (8 default)                         |
| -w         |               | size in characters or percent                    |
| -h         | --help        | display help                                     |

## Bindings

| binding | function                       |
| ------- | ------------------------------ |
| q       | quit                           |
| Q       | quit leaving the panes visible |
| c       | show command bindings          |
| r       | refresh                        |
| R       | reload                         |
| CTL-B   | page up                        |
| PGUP    | page up                        |
| SPACE   | page down                      |
| PGDN    | page down                      |
| CTL-F   | page down                      |
| j       | scroll down                    |
| k       | scroll up                      |
| DOWN    | scroll down                    |
| UP      | scroll up                      |
| gg      | go to the first line           |
| G       | go to the last line            |
| l       | move right                     |
| RIGHT   | move right                     |
| h       | move left                      |
| LEFT    | move left                      |
| /       | search                         |
| n       | find next                      |
| N       | find previous                  |
| gff     | fzf find                       |
| b       | fzf find                       |
| zl      | flip line number overlay       |
| zt      | flip line total display        |

# DEPENDENCIES

- Bash
- Perl
- FZF
- ansiexpand (https://github.com/tecolicom/App-ansiexpand) will fail back to *expand*

# INSTALL

Clone the repository and add it to your PATH; or link/copy the files to somewhere in your PATH.

# CONFIGURATION

The *paneless* file you run contains the configuration and bindings (press 'c' to see the bindings in FZF).

You can change the color used by *paneless* as well as the bindings (vim-like by default).

# AUTHORS

    Khemir Nadim ibn Hamouda
    https://github.com/nkh
    CPAN ID: NKH

# LICENCE

	© Nadim Khemir 2023, Artistic licence 2.0
