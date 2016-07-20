# Whizkers Utilities

Whizkers on its own is only a file templater. These scripts give you the ability to reload your themes on the fly!

Just clone the repo and add it to your $PATH!

## Overall Dependencies

* bash 4+
* [whizkers](https://github.com/metakirby5/whizkers)

Other dependencies are on a per-script basis.

## Rhisk

A script to easily switch between pre-configured whizkers templates.

Usage:

    rhisk - whizkers theme switch script
    Usage:
      rhisk [ optional args... ] - Rhisk

    Help Options:
      -h                      Show help options
    Theme Options:
      -o                      Show theme options
      -c                      Show all options uncategorized

### Autocomplete

#### Bash

The file `autocomplete` adds tab completion of the options for `rhisk`. To use it, you must source the file in your .bashrc.

#### Zsh

Similarly to Bash, you must source the file `autocomplete` in your .zshrc. However, before that, you must add the commands `autoload -U +X bashcompinit && bashcompinit` in order to use bash-style autocompletion in your shell.

## Autowzk

A script to generate colors and show a preview via whizkers and colorz2.

### Dependency:
* [colorz2](https://github.com/metakirby5/colorz2)

Usage:

    autowzk - whizkers theme generator
    Usage:
    autowzk [ command [ args... ] ] image file/URL
    If image URL provided, image will be saved at "~/.autowzk".
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

### Set the programs that reload

There is an array `programs` in the script, intended to declare the programs that need to be killed and reopened. Other configs are loaded if the appropriate files are detected.

## TODO

* Autowzk
	- [ ] Allow for template generation
	- [ ] Consolidate dependencies
	- [ ] Sort colors

* Reload-desktop
	- [x] Add font change controls
	    - [x] Make font change optional (Currently change function script variable)
	- [ ] Expand this to more wms/programs
		- [ ] Terminals
			- [x] URxvt/Rxvt/XTerm
			- [x] Termite
			- [ ] Terminator/Gnome-Terminal
			- [ ] st + [shit](https://github.com/neeasade/shit)
		- [ ] Window Managers
			- [x] i3
			- [ ] bspwm
			- [x] Openbox
			- [ ] Awesome
			- [ ] herbstluftwm
			- [ ] The many other popular wms not listed

## Thanks to

[metakirby5](https://github.com/metakirby5) for making any of this possible and creating whizkers.
