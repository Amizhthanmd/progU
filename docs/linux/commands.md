# Linux Commands

This guide presents the most essential Linux commands you’ll use for everyday tasks, organized by category.

---

## File and Directory Management

| Command      | Description                      | Example Usage                      |
| ------------ | -------------------------------- | ---------------------------------- |
| `ls`         | List directory contents          | `ls -l`                            |
| `cd`         | Change current directory         | `cd /path/to/dir`                  |
| `pwd`        | Show current directory           | `pwd`                              |
| `mkdir`      | Make new directory               | `mkdir new_folder`                 |
| `rmdir`      | Remove empty directory           | `rmdir old_folder`                 |
| `rm`         | Remove file/directory            | `rm file.txt`<br/>`rm -r dir`      |
| `cp`         | Copy files/directories           | `cp source dest`                   |
| `mv`         | Move or rename files/directories | `mv old_name new_name`             |
| `touch`      | Create an empty file             | `touch file.txt`                   |
| `cat`        | Display file contents            | `cat file.txt`                     |
| `nano`/`vim` | Edit files in terminal           | `nano file.txt`<br/>`vim file.txt` |

---

## System and User Management

| Command   | Description                 | Example Usage              |
| --------- | --------------------------- | -------------------------- |
| `sudo`    | Run commands as superuser   | `sudo apt update`          |
| `passwd`  | Change user password        | `passwd`                   |
| `adduser` | Add a new user              | `sudo adduser username`    |
| `deluser` | Delete a user               | `sudo deluser username`    |
| `chown`   | Change file/directory owner | `sudo chown user file.txt` |
| `chmod`   | Change file permissions     | `chmod 755 script.sh`      |
| `id`      | Show user identity          | `id`                       |
| `groups`  | Show group memberships      | `groups`                   |

---

## Package Management (Ubuntu/Debian)

| Command       | Description                | Example Usage           |
| ------------- | -------------------------- | ----------------------- |
| `apt update`  | Update package index       | `sudo apt update`       |
| `apt upgrade` | Upgrade installed packages | `sudo apt upgrade`      |
| `apt install` | Install a package          | `sudo apt install curl` |
| `apt remove`  | Remove a package           | `sudo apt remove nginx` |
| `apt search`  | Search for a package       | `apt search nginx`      |

---

## Disk and Process Management

| Command   | Description                | Example Usage       |
| --------- | -------------------------- | ------------------- |
| `df -h`   | Show disk usage            | `df -h`             |
| `du -sh`  | Show directory/file size   | `du -sh /home/user` |
| `top`     | Monitor system processes   | `top`               |
| `htop`    | Advanced process viewer    | `htop`              |
| `ps aux`  | List running processes     | `ps aux`            |
| `kill`    | Kill a process by PID      | `kill 12345`        |
| `killall` | Kill all processes by name | `killall firefox`   |
| `free -h` | Show memory usage          | `free -h`           |

---

## Networking

| Command         | Description                       | Example Usage                   |
| --------------- | --------------------------------- | ------------------------------- |
| `ping`          | Test network connectivity         | `ping example.com`              |
| `ip a`          | Show network interfaces           | `ip a`                          |
| `netstat -tuln` | Show open/listening ports         | `netstat -tuln`                 |
| `ss -ltn`       | Show listening TCP ports          | `ss -ltn`                       |
| `lsof -i -P -n` | List all open network connections | `lsof -i -P -n`                 |
| `lsof -i :80`   | Show processes using port 80      | `lsof -i :80`                   |
| `ssh`           | SSH to a remote machine           | `ssh user@host`                 |
| `scp`           | Copy files over SSH               | `scp file.txt user@host:/path/` |
| `wget`          | Download files from internet      | `wget http://example.com/file`  |
| `curl`          | Download or transfer data         | `curl -O http://url/file`       |

---

## Text Processing

| Command       | Description                 | Example Usage                        |
| ------------- | --------------------------- | ------------------------------------ |
| `grep`        | Search text patterns        | `grep "error" logfile.txt`           |
| `awk`         | Pattern scanning/processing | `awk '{print $1}' file.txt`          |
| `sed`         | Stream editor for text      | `sed 's/old/new/g' file.txt`         |
| `sort`        | Sort lines of text files    | `sort names.txt`                     |
| `head`/`tail` | Show start/end of files     | `head -10 file.txt`, `tail -20 file` |

---

## Miscellaneous

| Command    | Description               | Example Usage       |
| ---------- | ------------------------- | ------------------- |
| `echo`     | Print text to terminal    | `echo "Hello"`      |
| `history`  | Show command history      | `history`           |
| `clear`    | Clear terminal screen     | `clear`             |
| `shutdown` | Shutdown system           | `sudo shutdown now` |
| `reboot`   | Reboot system             | `sudo reboot`       |
| `date`     | Show date and time        | `date`              |
| `uname -a` | Show system information   | `uname -a`          |
| `man`      | Manual/help for a command | `man ls`            |
| `--help`   | Show command help         | `ls --help`         |

## Service Management Commands in Linux

The following table provides commonly used service management commands in Linux, particularly with `systemd` and `service`.

| Action            | systemctl Command                     | service Command                       |
| ----------------- | ------------------------------------- | ------------------------------------- |
| Start a service   | `systemctl start <service>`           | `service <service> start`             |
| Stop a service    | `systemctl stop <service>`            | `service <service> stop`              |
| Restart a service | `systemctl restart <service>`         | `service <service> restart`           |
| Reload a service  | `systemctl reload <service>`          | `service <service> reload`            |
| Enable at boot    | `systemctl enable <service>`          | `chkconfig <service> on`              |
| Disable at boot   | `systemctl disable <service>`         | `chkconfig <service> off`             |
| Check status      | `systemctl status <service>`          | `service <service> status`            |
| Show all services | `systemctl list-units --type=service` | `service --status-all`                |
| Check if enabled  | `systemctl is-enabled <service>`      | `chkconfig --list <service>`          |
| Mask a service    | `systemctl mask <service>`            | _(Not available in `service`)_        |
| Unmask a service  | `systemctl unmask <service>`          | _(Not available in `service`)_        |
| Reboot system     | `systemctl reboot`                    | `reboot`                              |
| Shutdown system   | `systemctl poweroff`                  | `shutdown now`                        |
| View logs         | `journalctl -u <service> -f`          | _(Check `/var/log/syslog` or others)_ |

> 🔹 Replace `<service>` with the actual service name (e.g., `nginx`, `ssh`, `docker`).

---
