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

## Reload-desktop

A script to reload configuration files in place.

### Set the programs that reload

There is an array `programs` in the script, intended to declare the programs that need to be killed and reopened. Other configs are loaded if the appropriate files are detected.

## TODO

* All
	- [ ] Increase Portability

* Rhisk
    - [ ] Expand functionality

* Autowzk
	- [ ] Allow for template generation
	- [ ] Consolidate dependencies
	- [ ] Sort colors

* Reload-desktop
	- [ ] Expand this to more wms/programs
