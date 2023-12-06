# Vim Commands

Save & exit Vim: `:wq`

## Cursor Movement

- Move cursor once:
  - `k`: Up
  - `j`: Down
  - `h`: Left
  - `l`: Right
- Move by words:
  - `w`: Forwards to the start of a word
  - `e`: Forwards to the end of a word
  - `b`: Backwards to the start of a word
  - `ge`: Backwards to the end of a word
- Move by words, where words can include punctuation:
  - `W`: Forwards to the start of a word
  - `E`: Forwards to the end of a word
  - `B`: Backwards to the start of a word
  - `gE`: Backwards to the end of a word
- Move in the current line:
  - `0`: Start of the line
  - `^`: First non-blank character
  - `g_`: Last non-blank character
  - `$`: End of the line
- Move to the beginning of the line at the:
  - `H`: Top of screen
  - `M`: Middle of screen
  - `L`: Bottom of screen
  - `gg`: First line of document
  - `G`: Last line of document
  - `5gg`, `5G`: 5th line of document
- Other movement:
  - `%`: Move to matching character, as in `(` to `)` (supports `()`, `{}`, `[]`)
  - `gd`: Local declaration
  - `gD`: Global declaration
  - `fx`: Move to next instance of character x
  - `5x`: Repeat movement command x 5 times

## Screen Movement

- `Ctrl + e`: move screen up one line without moving cursor
- `Ctrl + y`: move screen down one line without moving cursor
- `Ctrl + b`: move screen up one page & the cursor to the last line
- `Ctrl + f`: move screen down one page & the cursor to the first line
- `Ctrl + d`: move cursor and screen down 1/2 page
- `Ctrl + u`: move cursor and screen up 1/2 page

## Enter Insert Mode

- `i`: Insert before cursor
- `I`: Insert at the beginning of the line
- `a`: Insert after the cursor
- `A`: Insert at the end of the line
- `o`: Open a new line below the current line and begin inserting there
- `O`: Open a new line above the current line and begin inserting there
- `ea`: Append at the end of the word

## Commands During Insert Mode

- `Ctrl + h`: Delete the character before the cursor
- `Ctrl + w`: Delete the word before the cursor
- `Ctrl + j`: Add a line break at the cursor position
- `Ctrl + t`: Indent the line one time (moving right)
- `Ctrl + d`: De-indent the line one time (moving left)
- `Ctrl + rx`: Insert the contents of register `x`
- `Ctrl + ox`: Temporarily enter normal mode to do one command `x`

## Text Replacement

- `rx`: Replace character at cursor with character x
- `R`: Replace more than one character; keep replacing until `ESC` is pressed
- `J`: join the line below to the current line with 1 space in between

## Selecting Text

- `v`: Start selection (visual mode) before doing a command
- `V`: Start visual mode, but only select full lines
- `o`: Move to the other end of the selected area
