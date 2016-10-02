# Whizen Utilities

![example](https://raw.githubusercontent.com/fullsalvo/wz-utils/master/images/example.gif "Example usage")

Whizkers/Zenbu on their own are only file templaters. These scripts give you the ability to reload your themes on the fly!

Just clone the repo and add it to your $PATH!

## Overall Dependencies

* bash 4+
* [whizkers](https://github.com/metakirby5/whizkers) *OR* [zenbu](https://github.com/metakirby5/zenbu)

Other dependencies are on a per-script basis.

## Configuration

### whizkers/zenbu

For the sake of backwards compatibility, a new environment variable has been implemented. In your chosen shell's configuration file, you'll need to define the variable `RHISK_COMM` via `export RHISK_COMM="<whizkers/zenbu>"`.

### reload-desktop

`reload-desktop` now reads variables located in the defined `reload_config` file. By default, this will be `$HOME/.rhisk`. This can be altered by changing the `reload_config` variable in the script itself.

There are currently four variables defined in the configuration file:

- `reload_programs` -- programs that need to be restarted that can just be killed and restarted (e.g. Dunst, compton).
- `reload_key_programs` -- programs that need keypresses to reload (currently limited to single presses).
- `reload_keypresses` -- the keys to be pressed. key order must coincide with the order of programs.
- `reload_commands` -- scripts or other commands that, upon reload, must only be executed once.

### Example configuration

	reload_programs=( compton dunst )
	reload_key_programs=( emacs )
	reload_keypresses=( F13 )
	reload_commands=( foo.sh bar.sh )

`reload-desktop` will kill and restart compton and dunst, press F13 in emacs (which is likely bound to a function to reload its configuration), then run the scripts foo.sh and bar.sh.

Let it be noted that there are other programs that reload-desktop checks for and reconfigures on its own. Namely, these are

	 - XTerm and other X Terminal Emulators that use .Xresources (define the config location in `reload-desktop`)
	 - Termite
	 - cava
	 - tint2
	 - tmux (define the config location in `reload-desktop`)

# Script Information

## Rhisk

A script to easily switch between pre-configured whizkers/zenbu templates.

Usage:

    rhisk - whizkers/zenbu theme switch script
    Usage:
      rhisk [ optional args... ] - Rhisk

    Help Options:
      -h                      Show help options
    Theme Options:
      -o                      Show theme options
      -c                      Show all options uncategorized

### fzr

For those using junegunn's [fzf](https://github.com/junegunn/fzf), `fzr` allows you to select `rhisk` theme options from the list. Select multiple by using *TAB*, order being preserved.

### Autocomplete

#### Bash

The file `autocomplete` adds tab completion of the options for `rhisk`. To use it, you must source the file in your .bashrc.

#### Zsh

Similarly to Bash, you must source the file `autocomplete` in your .zshrc. However, before that, you must add the commands `autoload -U +X bashcompinit && bashcompinit` in order to use bash-style autocompletion in your shell.

## Autowzb

A script to generate colors and show a preview via whizkers/zenbu and colorz.

### Dependency:
* [colorz](https://github.com/metakirby5/colorz)

Usage:

    autowzb - whizkers/zenbu theme generator
    Usage:
    autowzb [ command [ args... ] ] image file/URL
    If image URL provided, image will be saved at "~/.autowzb".
    Available colors: black, red,  green, yellow,
                      blue, magenta, cyan, white

    Options:
      -h
            Show help options
      -p <color name>
            Set primary color for template
      -s <color name>
            Set secondary color for template
      -c
	        Include black and white in the templating
			  (default: no black and white)

## Reload-desktop

A script to reload program/wm configurations in place. Currently only used via calls in the other two scripts.

## WZGrab

A python script that parses Xresources text input from file or stdin and outputs a zenbu/whizkers-style
color template.

Usage:

	usage: wzgrab [-h] [-o OUTFILE] [-i INFILE] [-c CONFIG] [-s SETS]

	Parses .Xresources-formatted text and creates a whizkers/zenbu
	yaml-formatted template for colors. Can read from file or from
	stdin.

	optional arguments:
	  -h, --help  show this help message and exit
	  -o OUTFILE  output file name specification
	  -i INFILE   input file name specification
	  -c CONFIG   zenbu config folder specification, if not using the default.
				  (Default: /home/fullsalvo/.config/zenbu)
	  -s SETS     variable set directory, if not using the default. (Default:
				  variable_sets/)

## Thanks to

[metakirby5](https://github.com/metakirby5) for making any of this possible and creating whizkers and zenbu.
