# tmux

a terminal multiplexer

```bash
# list sessions
tmux ls
```

## Session

```bash
tmux new -s session_name

# keybind: <prefix>d
# detach tmux

# shorthand: a
tmux attach-session -t session_name
```

## Window

```bash
# open window in some directory
tmux new-window -c $HOME/dev

# open window then run shell, then close
tmux neww ./shell
```
