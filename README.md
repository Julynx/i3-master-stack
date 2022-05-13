### i3 vertical master & stack layout
Includes swapping functionality

Adapted from ___

## Installation

1) Download and place the files "master-stack" and "swapper" in your 
`~/.config/i3` directory.

2) Add the following lines to your `~/.config/i3/config`
```
#############
# AUTOSTART #
#############

exec --no-startup-id $HOME/.config/i3/master-stack


############
# BINDINGS #
############

bindsym $mod+Tab exec --no-startup-id $HOME/.config/i3/swapper
```

Note: You may have to restart i3 for the changes to take effect.

## Usage

The layout consists of a master window and a stack.
```
┌────────┬───────┐
│        │       │
│ Master │ Stack │
│        │       │
└────────┴───────┘
```
Opening a new window will set it as the master window, while
consecutive windows will be automatically inserted into the stack.

```
┌────────┬───────┐
│        │ Stack │
│ Master │┄┄┄┄┄┄┄│
│        │   +   │
└────────┴───────┘
```
Pressing the swapping keybinding (`$mod+Tab` by default) will
swap the focused window and the master window. 

```
┌───────┬───────┐    ┏━━━━━━━┓───────┐
│       │   2   │    ┃       ┃   2   │
│   1   ┢━━━━━━━┪ -> ┃   3   ┠───────┤
│       ┃   3   ┃    ┃       ┃   1   │
└───────┗━━━━━━━┛    ┗━━━━━━━┹───────┘
```
