# Interesting Info

## Regex examples from Aggietime

`_anum_pattern = "^[Aa][0-9]{8}$"`

A-number pattern:

- `^[Aa]`: starts with one of the items in the set A and a
- `[0-9]{8}`: contains exactly 8 characters in the set of numbers 0-9

`_pos_code_pattern = "^P(04|05|07|08|10)[0-9]{3}$"`

- `^P`: starts with P
- `(04|05|07|08|10)`: groups together the five numbers that could go next; `|` indicates either/or
- `[0-9]{3}`: contains a set of 3 characters that could be anything 0-9

`_unit_code_pattern = "^(GP|DP|UN)[A-Z\d]{3,4}$"`

- `^(GP|DP|UN)`: starts with a header for either group, department, or unit
- `[A-Z\d]`: the next set of characters could be any capital letter or a digit
- `{3,4}`: that set of characters will contain between 3 and 4 items, inclusive

## API call types

- GET - Used to retrieve a representation of a resource.
- POST - Used to create new new resources and sub-resources
- PUT - Used to update existing resources. the enclosed entity is considered to be a modified version of the resource stored on the origin server, and the client is requesting that the stored version be replaced
- PATCH - Used to update existing resources. the enclosed entity contains a set of instructions describing how a resource currently residing on the origin server should be modified to produce a new version
- DELETE - Used to delete existing resources
