## Neovim Buffers (`:ls`)

Running `:ls` shows active buffers.

Example output:

```
1  hR   "term://~/3178:/bin/zsh"    line 13
3  #hR  "term://~/3605:/bin/zsh"    line 8
6  %a   "~/.config/nvim/init.lua"   line 6
```

| <1> Buffer Number | <2> Status Flags | <3> Buffer Name/Path | <4> Cursor Location |
|-------------------|------------------|----------------------|---------------------|
| Unique buffer ID (`:b6`) | Buffer state (% current, # alternate, etc.) | Used for matching (`:b init.lua`) | Last cursor position |


## Buffer Flags

%  = current buffer
#  = alternate buffer (previous)
a  = active (visible)
h  = hidden
+  = modified (unsaved changes)
R  = readonly

## Useful Buffer Commands

:ls         → list buffers
:b <num>    → switch buffer by number
:b <name>   → switch buffer by name match
:bn         → next buffer
:bp         → previous buffer
Ctrl + ^    → toggle last buffer
:bd         → delete buffer

## Neovim Core Concepts

Buffer = content (file, terminal, help page)
Window = viewport (split showing buffer)
Tab    = layout container (group of windows)

