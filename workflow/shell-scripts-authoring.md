# Script distribution

## 1. node scripts

Shell tools for generic tasks

*   avoid scripts useless for others
*   avoid direct shell calls: use shell bindings bundled in npm packages
*   avoid using function declarations: use npm packages

## 2. bash scripts

Simple tasks for personal use

*   avoid more than 1 parameter
*   avoid flow control
*   avoid variable and function declaration
*   avoid source (include) scripts

Resources below are offered by bash as many ohters, but beware to use them:
they are a warning for migration to a more powerful platform like node.

*   avoid using bash extensions at all

Every script must be capable to be piped to a standard shell instance so you
can copy-paste them with `xclip`

    $ xclip < script
    $ xclip -o | sh

Reserve bash all-mighty powers to the command line

The migration may take a while because you need to isolate the behavior that
could be useful for other users, but the effort always is worthwhile **even if
you are its only user**

**Upd: Avoid using bash completely**

The rules below must be applied only on personal scripts, due to some tools:

*   `dotfiles`
*   `dotfiles-installer`
*   `shelljs` tools

So all bash scripting must be saved in private repos

## 3. bash aliases

Command shortcuts

*   shortcuts for shell commands and its parameters
