# Grep
grep = search tool
Example:
```bash
grep "hello" file.txt
```
Finds lines containing "hello".

## What are -Rin
These are flags (options) that change how grep behaves.

Each letter adds a feature.
-R = Recursive
Means:
👉 search inside folders AND subfolders.

Without -R, grep only searches one file.

With -R, it searches entire directory tree.

Example:
```bash
linux-notes/
   audio/pactl.md
   wayland/screenshot.md
```
-R searches all of them.

-i = ignore case
Search becomes case-insensitive.
So:
```text
pipewire
PipeWire
PIPEWIRE
```
all match.

-n = show line numbers
Output shows where in file the match exists.

Example:
```bash
audio/pactl.md:42:Install and start pipewire
```
Means:
Line 42.
SUPER useful

# Full command meaning
```bash
grep -Rin "pipewire" ~/linux-notes
```
Means:
search recursively
ignore case
show line numbers
for the word "pipewire"
inside your linux-notes folder

