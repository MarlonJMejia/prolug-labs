Detatch from tmux session and verify it is still there

Reconnect and then kill the session

Create a new tmux session with logging enabled to /root/tmuxlog.log

<br>

### Solution
<details>
<summary>Solution</summary>
Detatch from tmux session

```plain
ctrl + b and d
```

Verify that tmux session is still running

```plain
tmux -ls
```{{exec}}

Reconnect to that session

```plain
tmux a -t 0
```{{exec}}

Kill each window sessions, remember to press `y` after being prompted.

```plain
ctrl + b and y
```

Create a new session

```plain
tmux 
```
Log sesion output to a file

```plain
tmux pipe-pane -o "exec cat >>$HOME/'logs-tmux.log'"
```

Execute a command that keeps on running

```plain
while true; do uptime; sleep 1; done
```{{exec}}

Detach the tmux session

```plain
ctrl + b and d
```

View the pane log

```
cat $HOME/'logs-tmux.log'
```{{exec}}

</details>