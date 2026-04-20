# Tmux Configuration

Personal tmux configuration with custom keybindings, session management, and Tokyo Night theme.

> **Current Prefix:** `Ctrl` + `Space`

## Table of Contents
- [Installation](#installation)
- [Keybindings](#keybindings)
- [Sessionizer Script](#sessionizer-script)
- [Theme & Interface](#theme--interface)
- [Maintenance Commands](#maintenance-commands)

## Installation

1. Clone this repository or copy the files to your `~/.config/tmux/` directory:
   ```bash
   git clone <repository-url> ~/.config/tmux
   ```

2. Ensure the sessionizer script is executable:
   ```bash
   chmod +x ~/.config/tmux/tmux-sessionizer
   ```

3. Start tmux to load the configuration automatically

## Keybindings

### Session Management
| Action                                 | Shortcut       |
| :------------------------------------- | :------------- |
| **Sessionizer** (Project fuzzy finder) | `Prefix` + `f` |
| Detach from session (keep it running)  | `Prefix` + `d` |
| Reload configuration                   | `Prefix` + `r` |
| List active sessions (from Shell)      | `tmux ls`      |
| Attach to last session (from Shell)    | `tmux a`       |

### Pane Management
| Action                                | Shortcut                               |
| :------------------------------------ | :------------------------------------- |
| **Vertical Split** (side by side)     | `Prefix` + `v`                         |
| **Horizontal Split** (top/bottom)     | `Prefix` + `s`                         |
| **Quick Navigate** (No prefix needed) | `Alt` + `h` `j` `k` `l`                |
| Close current pane                    | `Prefix` + `x` (then `y`)              |
| Maximize / Restore pane (Zoom)        | `Prefix` + `m`                         |
| Resize Panes (Vim Style)              | `Prefix` + `h` `j` `k` `l` (hold keys) |

### Window Management (Tabs)
| Action                 | Shortcut                    |
| :--------------------- | :-------------------------- |
| Create new window      | `Prefix` + `c`              |
| Go to window by index  | `Prefix` + `1`, `2`, `3`... |
| Previous / Next window | `Prefix` + `p` / `n`        |
| Rename current window  | `Prefix` + `,`              |

### Copy Mode (Vim Style)
| Action                                | Shortcut       |
| :------------------------------------ | :------------- |
| Enter copy mode                       | `Prefix` + `[` |
| Start selection                       | `v`            |
| Copy selection (**wl-copy** / Fedora) | `y`            |
| Paste from buffer                     | `Prefix` + `P` |
| Exit copy mode                        | `Esc` or `q`   |

## Sessionizer Script

The `tmux-sessionizer` script provides a quick way to create and switch to project sessions using `fzf` for fuzzy finding.

### How it works:
1. Uses `fd` to find directories (excluding `.git` and `node_modules`) up to 3 levels deep
2. Pipes results to `fzf` for interactive selection
3. Creates a new tmux session named after the selected directory (with dots replaced by underscores)
4. If not in tmux, creates a new session; otherwise switches to it

### Dependencies:
- `fd` (find alternative)
- `fzf` (fuzzy finder)
- `tmux`

### Usage:
Press `Prefix` + `f` to launch the sessionizer, then type to search for your project directory.

## Theme & Interface

- **Theme:** Tokyo Night inspired
- **Status Bar:** Located at the **Bottom**
- **Window List:** Center-aligned
- **Active Window:** Highlighted with **Blue + Underscored**

## Maintenance Commands

- **Kill entire server:** `tmux kill-server`
- **Configuration file:** `~/.config/tmux/tmux.conf`
- **Sessionizer script:** `~/.config/tmux/tmux-sessionizer`

## Files in this configuration

- `tmux.conf` - Main tmux configuration
- `tmux-sessionizer` - Project session management script
- `README.md` - This documentation
