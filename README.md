# `del` command

Created by [Juan Ignacio Causse](mailto:juanignaciocausse@gmail.com).

---

## TL;DR

This command allows you to delete files and directories using the terminal and still be able to recover them.
* `del` deletes one or multiple files / directories. Usage: `del <FILE / DIR> [<FILE / DIR> ...]`
* `undel` recovers the last deleted file / directory. Usage: `undel`
See [installation](#Installation) instructions.

---

## Ever misused `rm`?
Accidental misuse of the `rm` command may lead to data loss, as files deleted with `rm` are usually non-recoverable.
This simple custom command, named `del` works by moving the files you want to delete to a "trash" directory located in your home, at `~/.deleted/`.

Inside that directory, you will find:
* **The "trash" directory**, named `trash`.
* **A log file**, named `deletions.log` to which all deletions are registered: every time you delete something, the original location of the deleted files and directories will be in the log.
* A file named **last_deletion** that is internally used to un-delete the last deleted file / directory. **DO NOT edit this file**.

The installation script will also create an alias for `rm`, which will prevent you from using it in interactive, non-root shell sessions.
**Non-interactive shell sessions are not affected** (so scripts can still use the original `rm`).
Running `sudo rm` **does** run the _actual_ `rm`, not the wrapper. This is very much intended.

---

## Features
* Deleted files and directories are completely recoverable. The `undel` custom command allows you to quickly recover the last deleted one.
* The log file holds the deletion date and time, and the original path of each deleted file and directory.
* Non-interactive shell sessions are not affected.
* On interactive shell sessions, `rm` is disabled using a wrapper.
* Running `rm` using `sudo` runs the actual `rm`, not the wrapper.
* Ultra-lightweight and open source.
* Very simple, non-privileged installation.

---

## Installation
1. Download this repository as zip. Unzip it and place a terminal inside its directory.
2. Run:
```bash:
./install
```
3. Restart your terminal.

