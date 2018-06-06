# Git

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Configuration](#configuration)
  - [SSH/HTTPS](#sshhttps)
  - [Some aliases](#some-aliases)
  - [CRLF conversion](#crlf-conversion)
    - [core.autocrlf=true](#coreautocrlftrue)
    - [core.autocrlf=input](#coreautocrlfinput)
    - [core.autocrlf=false](#coreautocrlffalse)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Configuration

### SSH/HTTPS

Force git to use HTTPS URLs over SSH:

    git config --global url."https://".insteadOf git://

### Some aliases

- gl="git log --pretty='%ci %Cred%h %Creset%s %Cgreen(%an)'"
- gg="git log --oneline --graph --decorate"
- gb="git branch -vva"
- gs="git status"

### CRLF conversion

#### core.autocrlf=true

- Local -> Remote = CRLF -> LF
- Remote -> Local = LF -> CRLF

Set to _true_ on Windows.

#### core.autocrlf=input

- Local -> Remote = CRLF -> LF
- Remote -> Local = no modification

Set to _input_ to avoid (auto)generated files with CRLF to be pushed on remote.

#### core.autocrlf=false

- Local -> Remote = no modification
- Remote -> Local = no modification

Set to _false_ in non-Windows environments.
