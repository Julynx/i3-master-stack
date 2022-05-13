# i3 vertical master & stack layout
Includes swapping functionality

_Adapted from [Christian Tenllado](https://github.com/tenllado)
and [YourArmpitStinks](https://www.reddit.com/user/YourArmpitStinks/)._

## Installation

1) Download and place the files [master-stack](https://raw.githubusercontent.com/Julynx/i3-master-stack/main/master-stack) and [swapper](https://raw.githubusercontent.com/Julynx/i3-master-stack/main/swapper) in your 
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

3) You may have to restart i3 or log out and log back in for the changes to take effect.

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
Pressing the swapping keybind `$mod+Tab` will
swap the focused window and the master window. 

```
┌───────┬───────┐    ┏━━━━━━━┓───────┐
│       │   2   │    ┃       ┃   2   │
│   1   ┢━━━━━━━┪ -> ┃   3   ┠───────┤
│       ┃   3   ┃    ┃       ┃   1   │
└───────┗━━━━━━━┛    ┗━━━━━━━┹───────┘
```
