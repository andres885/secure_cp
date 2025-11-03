# secure_cp

**secure_cp** is a lightweight Bash script for creating structured backups of virtual servers or development environments.  
It automatically generates sequential backup directories (e.g. `DocumentRoot.001`, `DocumentRoot.002`, …), excludes specified directories, and preserves previous backups to maintain a clear version history.

---

## Features

- Creates automatically numbered backup directories.
- Prevents overwriting existing backups.
- Skips redundant or heavy data (such as images or videos) according to your exclusion rules.
- Simple and fast – ideal for local or remote server backup routines.

---

## Usage

1. **Download the script**

   Save the `secure_cp` file to your preferred location and make it executable:

   ```bash
   chmod +x secure_cp
   ```

   ---

## 2. Edit configuration paths

Open the script with your preferred text editor and modify the following lines to match your environment:

```bash
ORIGEN="/var/www/DocumentRoot"
DESTINO_BASE="/home/usuario/Desarrollo/Web/Example/bkp"
NOMBRE_BASE="DocumentRoot"
```

- `ORIGEN` → path to your source directory (e.g., your web root).  
- `DESTINO_BASE` → directory where backups will be stored.  
- `NOMBRE_BASE` → base name used for the backup directories.

## 3. Run the script

Execute the script from your terminal:

```bash
./secure_cp
```

The script will create a new backup directory such as:

```
/home/usuario/Desarrollo/Web/Example/bkp/DocumentRoot.001
```

Each new execution will increment the backup index automatically (`DocumentRoot.002`, `DocumentRoot.003`, …).

---

## Example

If your document root is `/var/www/html` and you want to store backups in `/mnt/backups/html`, you would set:

```bash
ORIGEN="/var/www/html"
DESTINO_BASE="/mnt/backups/html"
NOMBRE_BASE="html"
```

Then simply run:

```bash
./secure_cp
```

---
