---
categories:
- professional
date: "2022-07-31T00:00:00Z"
tags:
- linux
- programming
title: Linux Shell Key Bindings
---
By default, bash (and zsh & fish too) is configured with line editing commands similar to those of Emacs. It can also be switched to a vi-style interface.

In vi mode, press `Esc` to switch to command mode and press `i` to switch to insert mode.

| Action | Emacs | vi |
| ------ | ----- | -- |
| Move forward one character | Ctrl f | l |
| Move backward one character | Ctrl b | h |
| Move to start of line | Ctrl a | 0 |
| Move to end of line | Ctrl e | $ |
| Move forward a word | Alt f | w |
| Move backward a word | Alt b | b |
| Cut (delete) to end of line | Ctrl k | d$ |
| Cut (delete) to beginning of line | Ctrl u | d0 |
| Cut (delete) to the start of the current word | Alt Del | db |
| Cut (delete) to the previous whitespace | Ctrl w ||
| Cut (delete) to the end of the current word | Alt d | dw |
| Paste from buffer | Ctrl y |  |
| Move to next line in history | Ctrl n | j |
| Move to previous line in history | Ctrl p | k |
| Search backwards in history | Ctrl r ||
| Search forwards in history | Ctrl s ||
| Insert last command from history | !! ||
| Clear screen | Ctrl l ||
| Activate in bash | `set -o emacs` (Default) | `set -o vi` |
| Activate in zsh | `bindkey -e` (Default) | `bindkey -v` |
