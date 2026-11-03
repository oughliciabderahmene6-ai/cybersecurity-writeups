# OverTheWire Bandit: Levels 0 to 7

## Goal
Bandit is a beginner wargame that teaches Linux command-line basics.
Each level hides a password that gives access to the next one over SSH.

## Approach and commands used

| Level | Challenge | Key command | What I learned |
|-------|-----------|-------------|----------------|
| 0 | Connect to the server | `ssh bandit0@bandit.labs.overthewire.org -p 2220` | SSH connection on a non-default port |
| 1 | File named `-` | `cat ./-` | A leading dash is read as an option, so a path is needed |
| 2 | Spaces in the file name | `cat "spaces in this filename"` | Quoting or escaping special characters |
| 3 | Hidden file | `ls -a` then `cat .hidden` | Files starting with `.` are hidden |
| 4 | Only readable file | `file ./*` | `file` identifies file types |
| 5 | Size and permissions | `find . -type f -size 1033c ! -executable` | `find` filters by size and permissions |
| 6 | Owner, group, size | `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` | `2>/dev/null` hides permission errors |
| 7 | Word in a big file | `grep millionth data.txt` | `grep` searches text quickly |

## Key takeaways
- Linux file permissions and ownership are central to security.
- `find` and `grep` are essential for searching a system.
- Always check what a command does before running it (`man <command>`).

## Security perspective
Misconfigured permissions and passwords stored in readable files are
common real-world weaknesses.
