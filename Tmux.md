# Tmux
Source: [YouTube](https://www.youtube.com/watch?v=En4wcQnY2Og&list=WL&index=7&t=651s)

Tmux is a terminal multiplexer that allows you to manage multiple terminal sessions, panes, and windows.

**************************

- pane < window < session

### Tmux Commands:
- `tmux att -t 0` or `tmux attach -t 0`: Open (attach) session 0
- `tmux ls`: List sessions
- `tmux new -s X`: Create a new session named X

### cntrl + b:
#### Pane Management:
- `set -g mouse on`: Enable scroll with the mouse

- `%`: Split the current pane into two, left and right
- `"`: Split the current pane into two, top and bottom
- `t`: Show time

- Arrow keys: Move between panes
- `cntrl + arrow keys` or `esc + arrow keys`: Resize the current pane

- COMMANDS:
  - `:resize-pane -D`: Resizes the current pane down
  - `:resize-pane -U`: Resizes the current pane up
  - `:resize-pane -L`: Resizes the current pane left
  - `:resize-pane -R`: Resizes the current pane right
  - `:resize-pane -D 10`: Resizes the current pane down by 10 cells
  - `:resize-pane -U 10`: Resizes the current pane up by 10 cells
  - `:resize-pane -L 10`: Resizes the current pane left by 10 cells
  - `:resize-pane -R 10`: Resizes the current pane right by 10 cells
  - `:setw synchronize-panes on`: Synchronize all panes in the current window
  - `:setw synchronize-panes off`: Desynchronize all panes in the current window
  - `:set -g status off`: Hide the status bar

- `z`: Zoom in on the current pane
- `z`: Zoom out on the current pane

#### Window Management:
- `c`: Create a new window
- `,`: Rename the current window
- `w`: List windows
- `&`: Kill the current window

#### Pane and Session Management:
- `x`: Kill the current pane
- `d`: Detach from the current session

**************************

