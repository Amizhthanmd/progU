# File Permissions

Linux file permissions are a core part of the operating system's security model. They determine who can read, write, or execute files and directories.

---

## Understanding the Permission Format

Run `ls -l` in a terminal to see file permissions:

```bash
ls -l
```

Example:

```
-rwxr-xr-- 1 user group 1234 Jul 20 10:00 example.sh
```

Breakdown:

```
[File Type][User][Group][Others]
-rwx        r-x    r--
```

### File Type

- `-` : Regular file
- `d` : Directory
- `l` : Symbolic link

### Permission Characters

- `r` : Read
- `w` : Write
- `x` : Execute
- `-` : No permission

---

## Permission Categories

1. **User (Owner)** – Permissions for the file's owner
2. **Group** – Permissions for the group associated with the file
3. **Others** – Permissions for everyone else

Each permission category contains 3 characters: `r`, `w`, and `x`.

---

## Numeric (Octal) Representation

Each permission set maps to a number:

| Permission | Binary | Octal |
| ---------- | ------ | ----- |
| `r`        | 100    | 4     |
| `w`        | 010    | 2     |
| `x`        | 001    | 1     |

### Examples:

| Symbolic    | Octal | Meaning                               |
| ----------- | ----- | ------------------------------------- |
| `rwxr-xr-x` | 755   | Owner: all, Group/Others: read + exec |
| `rw-r--r--` | 644   | Owner: read/write, others: read only  |
| `rwx------` | 700   | Only owner can read/write/execute     |

---

## Changing Permissions

### `chmod` – Change file mode (permissions)

#### Symbolic Mode:

```bash
chmod u+x file     # Add execute to user
chmod g-w file     # Remove write from group
chmod o=r file     # Set read-only for others
```

#### Numeric Mode:

```bash
chmod 755 file     # Set rwxr-xr-x
```

### `chown` – Change file owner

```bash
chown user:group file
```

### `chgrp` – Change group ownership

```bash
chgrp groupname file
```

---

## Directory Permissions

- `r` : List contents (e.g., `ls`)
- `w` : Create/delete files in the directory
- `x` : Enter the directory (e.g., `cd`)

> To access a directory, execute (`x`) permission is required.

---

## Special Permissions

1. **SetUID (`s`)** – Runs the file as the file owner (user)
2. **SetGID (`s`)** – Runs the file as the group owner or preserves group in directories
3. **Sticky Bit (`t`)** – In directories, only file owners can delete their own files

```bash
chmod u+s filename   # SetUID
chmod g+s filename   # SetGID
chmod +t directory   # Sticky bit
```

---

## Quick Practice

```bash
touch testfile
chmod 755 testfile
ls -l testfile
```

Expected output:

```
-rwxr-xr-x 1 user group 0 Jul 20 10:00 testfile
```

---

## Summary Table

| Symbol | Meaning      | Who         |
| ------ | ------------ | ----------- |
| `r`    | Read         | View file   |
| `w`    | Write        | Edit file   |
| `x`    | Execute      | Run file    |
| `u`    | User (owner) | File owner  |
| `g`    | Group        | Group users |
| `o`    | Others       | Everyone    |
| `a`    | All          | u + g + o   |

---

## Calculate Permissions Easily

Use this online tool to calculate symbolic and numeric permissions:

👉 [https://chmod-calculator.com/](https://chmod-calculator.com/)

---
