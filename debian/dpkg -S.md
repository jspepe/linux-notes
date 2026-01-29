# dpkg -S — who installed this file?

## What this command does

The `-S` flag searches for which package owns a specific file. It's useful when you want to know which Debian package installed a particular file on your system.

## Syntax

```bash
dpkg -S [PATTERN]
```

## Basic Examples

### Find which package owns a specific file:
```bash
dpkg -S /usr/bin/startx
# Output: xinit: /usr/bin/startx
```

### Search for a file pattern:
```bash
dpkg -S /etc/apt
# Lists all files from packages in /etc/apt/
```

### Search by filename (not full path):
```bash
dpkg -S grep
# Finds which package installed any file containing "grep"
```

## Common Use Cases

### Find which package installed a command:
```bash
dpkg -S /usr/bin/python3
```

### Search for configuration files:
```bash
dpkg -S /etc/ssh/sshd_config
```

### Find library ownership:
```bash
dpkg -S /lib/x86_64-linux-gnu/libc.so.6
```

## Useful Flags

### `-l` (list): Show long format with package version
```bash
dpkg -S -l /usr/bin/vim
```

### `-a` (all): Search in all packages (not just installed)
```bash
dpkg -S -a /usr/bin/some_file
```

### Wildcards and patterns:
```bash
# Find all files in a directory
dpkg -S '/usr/share/doc/*'

# Find files matching a pattern
dpkg -S '*/bin/python*'
```

## Related Commands

| Command | Purpose |
|---------|---------|
| `dpkg -L package` | List all files installed by a package |
| `dpkg -l` | List all installed packages |
| `apt-file search FILE` | Search files in packages (more comprehensive, includes uninstalled) |
| `which command` | Find location of a command in PATH |

## Tips

- **Case-sensitive**: Pattern matching is case-sensitive
- **Partial matches work**: You don't need the full path; `dpkg -S grep` will find any file with "grep" in the name
- **Only installed packages**: By default, `dpkg -S` only searches installed packages
- **For uninstalled packages**: Use `apt-file search` instead (requires `apt-file install` first)
