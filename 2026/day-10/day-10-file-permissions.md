Great 🙌 Here is your **GitHub markdown file** with the **same content as the blog**, ready to copy and paste.

Save this as:
`day-10-file-permissions.md`

---

````markdown
# 🐧 Day 10 – Linux File Permissions & File Operations

Today’s goal was to understand how Linux file permissions work and how to perform basic file operations like creating, reading, and modifying files.

---

# 📁 Task 1 — Create Files

### 1️⃣ Create an empty file using `touch`

```bash
touch devops.txt
```

**Explanation:**  
Creates a blank file named `devops.txt`.

---

### 2️⃣ Create a file with content using `echo`

```bash
echo "Linux permissions are important" > notes.txt
```

**Explanation:**
- `echo` prints text
- `>` redirects that text into a file (overwrites if it exists)

---

### 3️⃣ Create a script using `vim`

```bash
vim script.sh
```

Inside vim, add:

```bash
echo "Hello DevOps"
```

Save and exit:
```
Esc → :wq → Enter
```

---

### 🔍 Verify Files

```bash
ls -l
```

You might see:

```
-rw-r--r-- devops.txt
-rw-r--r-- notes.txt
-rw-r--r-- script.sh
```

---

# 📖 Task 2 — Read Files

### 1️⃣ Read full file

```bash
cat notes.txt
```

Displays the entire file content.

---

### 2️⃣ Open file in read-only mode

```bash
vim -R script.sh
```

Prevents accidental editing.

---

### 3️⃣ Show first 5 lines of a file

```bash
head -n 5 /etc/passwd
```

Used to preview the beginning of a file.

---

### 4️⃣ Show last 5 lines

```bash
tail -n 5 /etc/passwd
```

Useful for checking recent entries in logs.

---

# 🔐 Task 3 — Understand Permissions

Run:

```bash
ls -l
```

Example output:

```
-rw-r--r--
```

### Permission breakdown:

| Section | Meaning |
|--------|---------|
| First `rw-` | Owner can read & write |
| Second `r--` | Group can read |
| Third `r--` | Others can read |

---

### Permission Numbers

| Permission | Value |
|-----------|------|
| r | 4 |
| w | 2 |
| x | 1 |

Examples:
- `7` = rwx (4+2+1)
- `6` = rw- (4+2)
- `5` = r-x (4+1)

---

# ✏️ Task 4 — Modify Permissions

### 1️⃣ Make script executable

```bash
chmod +x script.sh
./script.sh
```

Now the script can run.

---

### 2️⃣ Make file read-only

```bash
chmod -w devops.txt
```

Removes write permission.

---

### 3️⃣ Set specific permission (640)

```bash
chmod 640 notes.txt
```

Meaning:
- Owner → read & write
- Group → read only
- Others → no access

---

### 4️⃣ Create directory with 755 permission

```bash
mkdir project
chmod 755 project
```

Meaning:
- Owner full access
- Others can read and enter, but not write

---

# 🧪 Task 5 — Test Permissions

### Try writing to read-only file

```bash
echo "test" >> devops.txt
```

Output:
```
Permission denied
```

---

### Try executing non-executable file

```bash
./notes.txt
```

Output:
```
Permission denied
```

---

# 🧠 What I Learned

1. How to create files using `touch`, `echo`, and `vim`  
2. How to read files using `cat`, `head`, and `tail`  
3. How Linux permissions work using `rwx` and numbers  
4. How to safely change permissions using `chmod`
````

---

If you want, next I can run a **live Day 10 permission simulation lab** where you break and fix file permissions like real troubleshooting 🔧
