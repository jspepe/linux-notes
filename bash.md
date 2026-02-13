# Bash / Readline Editing Shortcuts
These shortcuts are provided by GNU Readline and work in many terminal programs.

| Shortcut | Action |
|----------|--------|
| Ctrl + A | Move cursor to beginning of line |
| Ctrl + E | Move cursor to end of line |
| Alt + B | Move back one word |
| Alt + F | Move forward one word |
| Ctrl + W | Delete previous word |
| Ctrl + U | Delete from cursor to beginning |
| Ctrl + K | Delete from cursor to end |
| Ctrl + R | Reverse search command history |
| Ctrl + L | Clears the terminal |

## Aliases
How to check all your Aliases
```bash
alias
```
### Nextcloud OCC 
```bash
alias occ='docker exec -u www-data nextcloud-app php occ'
```
`occ` is the Nextcloud command-line admin tool.

It runs inside the Nextcloud container and lets you manage the app
without using the web UI.

| Example           | Command            |
|-------------------|--------------------|
| list users        | user:list          |
| user info         | user:info USERNAME |
| delete user       | user:delete USERNAME |
| manage apps       | app:list           |
| enable app        | app:enable APPNAME |
| disable app       | app:disable APPNAME |
| maintenance mode  | maintenance:mode --on |
| maintenance off   | maintenance:mode --off |
| background jobs   | background:cron    |
| system status     | status             |

So running:

occ user:list

actually executes the OCC command inside the Docker container.
