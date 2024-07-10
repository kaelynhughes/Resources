# Command Cheatsheet

## Aliases

```zsh
git commit -m -> gc
git add -> ga
git push -> gp
python3 -> py
```

## `tmux` Commands

Note 0: Precede each of these with `Ctrl + b`

Note 1: Bottom bar contains the numbers and names associated with each name, plus a `*` after the active window and a `-` after the last active window

### Windows
- `c`: Create window 
- `,`: Rename current window
- `w`: List windows
- numbers `0-9`: Switch to the associated window
- `l`: Toggle last active window
- `&`: Close current window

### Panes 

- `"`: Split window vertically
- `%`: Split window horizontally
- `x`: Kill current pane 
- `{`: Move current pane left
- `}`: Move current pane right
- Arrows: Switch panes in the direction the arrow is pointing
- `q`: Show pane numbers
- `q` + number `0-9`: Select pane by number
- 

## Other stuff for command line

````
Check what is running on a port:
* `lsof` = `ls` open files
* `-P`: tells shell not to convert port numbers to port names
    * Can instead do `-nP` if I want to see network numbers instead of network names, eg. 127.0.0.1 instead of localhost
* `-iTCP:5000`: specifies which port
* `grep`: search for a keyword
```zsh
sudo lsof -P -i :[port number]
````

## VSCode Keyboard Shortcuts

- Search for a command: `Cmd + Shift + P`
- Open/close a terminal window: `Ctrl + ` `
- Search the current file: `Cmd + F`; add `Shift` to search the current directory instead
- Preview a markdown file: `Cmd + Shift + V`
- Open/close sidebar: `Cmd + B`
- Select word: `Cmd + D` (press multiple times to also select subsequent occurrences of that word)
- Select line: `Cmd + L` (press multiple times to also select subsequent lines)
- Delete line: `Cmd + Shift + K`
- Split editor: `Cmd + [\, 2, 3, 4]` depending on how many you already have up
  - Switch between sections: `Cmd+
- Move line(s) up/down: `Opt + [↑/↓]`; add `Shift` to copy instead of moving
- Format code: `Opt + Shift + F`
- Peek definition: `Opt + F12`
- Rename a component: `F2`

## Rectangle (window manager)

_These are my personal preferences for [the Rectangle window manager](https://rectangleapp.com/) for Mac._

- Left/right/top/bottom half: `Cmd + Opt + [arrow key]`
- Top left/right: `Cmd + Ctrl + [←/→]`
- Bottom left/right: `Cmd + Ctrl + Shift + [←/→]`
- Maximize: `Ctrl + Opt + Enter`
- Maximize height: `Ctrl + Opt + Shift + ↑`
- Leftmost fourth (for terminal, notes): `Cmd + Ctrl + ↑`
- Second leftmost fourth (for browser?): `Cmd + Ctrl + ↓`

## Other helpful keyboard shortcuts

- Inspector tools: `Cmd + Opt + I`
- Go to mobile view within a Firefox window: `Cmd + Shift + M`
- Full-screen current tab (excluding VSCode): `Cmd + Shift + F`
- docker compose -f [docker compose file] up [--build]
  - build command rebuilds the container

## fzf commands

_These commands available through [junegunn's fzf package](https://github.com/junegunn/fzf) - install through homebrew ↓_

```
brew install fzf
```

- Enter interactive finder: `fzf`
- Move up in the list: `Ctrl + K` or `Ctrl + P`
- Move down in the list: `Ctrl + J` or `Ctrl + N`
- Exit interactive finder: `Esc` or `Ctrl + C` or `Ctrl + G`
