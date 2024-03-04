Visit the dictionary at: https://szdytom.github.io/infinite-craft-dictionary/

Source code (non-minimized): https://github.com/szdytom/infinite-autocraft

## File format

The dictionary database is contained in the file with extension ".zst".
It is compressed with `zstd`. Uncompress it with `unzstd`.
The uncompressed ".dat" file will be formatted as follows.
All fields are stored little-endian.

- The element id of element “Nothing”: 2 bytes
- Count of elements: 4 bytes
- For each element:
  - A unique element id: 2 bytes
  - Length of name, in bytes: 4 bytes
  - Name, in UTF-8 encoding, no trailing \0
  - Length of emoji string, in bytes: 4 bytes
  - Emoji string, in UTF-8 encoding, no trailing \0
  - Recipe id that can craft the element: 4 bytes
  - Crafting depth: 2 bytes
- Count of recipes: 4 bytes
- For each recipe:
  - A unique recipe id: 4 bytes
  - Element id of the first input: 2 bytes
  - Element id of the second input: 2 bytes
  - Element id of the result: 2 bytes
