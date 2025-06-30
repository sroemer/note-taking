# Notes

## Table of Contents

<!-- toc -->

- [Bash](#bash)
  * [Keyboard Shortcuts](#keyboard-shortcuts)
    + [Command Editing Shortcuts](#command-editing-shortcuts)
    + [Command Recall Shortcuts](#command-recall-shortcuts)
    + [Command Control Shortcuts](#command-control-shortcuts)
    + [Bash Bang (!) Commands](#bash-bang--commands)
  * [Special Variables](#special-variables)
  * [Avoid reading/writing to the same file](#avoid-readingwriting-to-the-same-file)
- [Gentoo Linux](#gentoo-linux)
  * [Portage](#portage)
  * [Kernel / Bootloader](#kernel--bootloader)
- [Linux Development](#linux-development)
  * [List exported symbols of libraries](#list-exported-symbols-of-libraries)
    + [nm](#nm)
    + [objdump](#objdump)
    + [readelf](#readelf)
- [Python](#python)
  * [Virtual Environment](#virtual-environment)

<!-- tocstop -->

## Bash

### Keyboard Shortcuts

#### Command Editing Shortcuts

- ```Ctrl + a```      go to the start of the command line
- ```Ctrl + e```      go to the end of the command line
- ```Ctrl + k```      delete from cursor to the end of the command line
- ```Ctrl + u```      delete from cursor to the start of the command line
- ```Ctrl + w```      delete from cursor to start of word (i.e. delete backwards one word)
- ```Ctrl + y```      paste word or text that was cut using one of the deletion shortcuts (such as
                the one above) after the cursor
- ```Ctrl + xx```     move between start of command line and current cursor position (and back again)
- ```Alt + b```       move backward one word (or go to start of word the cursor is currently on)
- ```Alt + f```       move forward one word (or go to end of word the cursor is currently on)
- ```Alt + d```       delete to end of word starting at cursor (whole word if cursor is at the
                beginning of word)
- ```Alt + c```       capitalize to end of word starting at cursor (whole word if cursor is at the
                beginning of word)
- ```Alt + u```       make uppercase from cursor to end of word
- ```Alt + l```       make lowercase from cursor to end of word
- ```Alt + t```       swap current word with previous
- ```Ctrl + f```      move forward one character
- ```Ctrl + b```      move backward one character
- ```Ctrl + d```      delete character under the cursor
- ```Ctrl + h```      delete character before the cursor
- ```Ctrl + t```      swap character under cursor with the previous one

#### Command Recall Shortcuts

- ```Ctrl + r```      search the history backwards
- ```Ctrl + g```      escape from history searching mode
- ```Ctrl + p```      previous command in history (i.e. walk back through the command history)
- ```Ctrl + n```      next command in history (i.e. walk forward through the command history)
- ```Alt + .```       use the last word of the previous command

#### Command Control Shortcuts

- ```Ctrl + l```      clear the screen
- ```Ctrl + s```      stops the output to the screen (for long running verbose command)
- ```Ctrl + q```      allow output to the screen (if previously stopped using command above)
- ```Ctrl + c```      terminate the command
- ```Ctrl + z```      suspend/stop the command

#### Bash Bang (!) Commands

- ```!!```            run last command
- ```!/word/```       run the most recent command that starts with /word/ (e.g. !ls)
- ```!/word/:p```     print out the command that \!/word/ would run (also adds it as the latest
                command in the command history)
- ```!$```            the last word of the previous command (same as Alt + .)
- ```!$:p```          print out the word that \!\$ would substitute
- ```!*```            the previous command except for the last word
- ```!*:p```          print out what \!\* would substitute

### Special Variables

- ```$0```            the command running
- ```$1-$n```         argument 1 - n
- ```$@```            list of all arguments
- ```$#```            number of arguments
- ```$*```            all arguments separated by IFS (use $@ to avoid whitespace issues)
- ```$$```            process id of the shell the command is running in
- ```$?```            exit code of previous command
- ```$!```            process id of most recent background process
- ```$IFS```          the internal field separator

### Avoid reading/writing to the same file

Read all of some/file into memory before writing it to some-command's stdin.
This lets some-command's stdout be redirected to some/file without the usual
problems of reading/writing from the same file.

```bash
some-command <<<"$(< some/file)" >some/file
```

## Gentoo Linux

### Portage

- ```emerge-webrsync```                           # Sync
- ```emerge --update --deep --newuse @world```    # Update
- ```emerge --depclean```                         # Cleanup

### Kernel / Bootloader

- ```eclean-kernel -n <N>```    # Remove old kernel versions, but keep the N newest kernels# Development

## Linux Development

### List exported symbols of libraries

#### nm

- -D: show dynamic symbols (dynamic libraries)
- -C: demangle (show C++ source identifiers)
- -U: show defined symbols only
- -g: show external only (static libraries)

#### objdump

- -T: show dynamic symbols (dynamic libraries)
- -C: demangle (show C++ source identifiers)

#### readelf

- -W: wide output (do not break lines into 80 columns)
- -s: show symbols
- --dyn-syms: show dynamic symbols (dynamic libraries)
- --demangle: demangle (show C++ source identifiers)

## Python

### Virtual Environment

1. ```python3 -m venv .venv```
2. ```source .venv/bin/activate```
