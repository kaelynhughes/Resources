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

## Text Replacement

- `rx`: Replace character at cursor with character x
