
---

# 🐧 LINUX COMMANDS – PRACTICAL LEARNING GUIDE (WSL Friendly)

---

# 📁 1. File & Directory Operations (Start Here First)

## 1️⃣ `pwd` – Where am I?

Print current directory.

```bash
pwd
```

👉 Shows your current folder path.

---

## 2️⃣ `ls` – List files

```bash
ls
```

Detailed view:

```bash
ls -l
```

Show hidden files:

```bash
ls -a
```

---

## 3️⃣ `cd` – Change directory

Go into folder:

```bash
cd Desktop
```

Go back one level:

```bash
cd ..
```

Go home:

```bash
cd
```

---

## 4️⃣ `mkdir` – Create directory

```bash
mkdir linux_practice
```

Enter it:

```bash
cd linux_practice
```

---

## 5️⃣ `touch` – Create file

```bash
touch file1.txt
```

Create multiple files:

```bash
touch file2.txt file3.txt
```

Check:

```bash
ls
```

---

## 6️⃣ `cp` – Copy file

```bash
cp file1.txt copy_file1.txt
```

Copy folder:

```bash
cp -r linux_practice backup_folder
```

---

## 7️⃣ `mv` – Move or Rename

Rename:

```bash
mv file2.txt renamed.txt
```

Move:

```bash
mv renamed.txt ../
```

---

## 8️⃣ `rm` – Delete

Delete file:

```bash
rm file3.txt
```

Delete folder:

```bash
rm -r backup_folder
```

⚠️ Be careful with `rm -r`

---

## 9️⃣ `ln` – Create link

Hard link:

```bash
ln file1.txt hardlink.txt
```

Soft link:

```bash
ln -s file1.txt softlink.txt
```

---

## 🔟 `find` – Search files

```bash
find . -name "file1.txt"
```

Find all txt files:

```bash
find . -name "*.txt"
```

---

# 📝 2. File Viewing & Editing

---

## 1️⃣ `cat` – View file

```bash
cat file1.txt
```

Write inside file:

```bash
echo "Hello Linux" > file1.txt
cat file1.txt
```

---

## 2️⃣ `less` – Scroll view

```bash
less file1.txt
```

Press `q` to quit.

---

## 3️⃣ `head` & `tail`

```bash
head file1.txt
tail file1.txt
```

Show last 5 lines:

```bash
tail -5 file1.txt
```

---

## 4️⃣ `nano` – Simple editor

```bash
nano file1.txt
```

Edit → Press `CTRL+X` → Save

---

## 5️⃣ `echo` – Print text

```bash
echo "Learning Linux"
```

Append to file:

```bash
echo "Second line" >> file1.txt
```

---

## 6️⃣ `tee` – Save + display

```bash
echo "Third line" | tee newfile.txt
```

Append:

```bash
echo "Fourth line" | tee -a newfile.txt
```

---

# 🔍 3. Text Processing

---

## 1️⃣ `grep` – Search text

```bash
grep "Linux" file1.txt
```

Case insensitive:

```bash
grep -i "linux" file1.txt
```

---

## 2️⃣ `sort`

```bash
sort file1.txt
```

Numeric:

```bash
sort -n numbers.txt
```

---

## 3️⃣ `uniq`

```bash
sort file1.txt | uniq
```

---

## 4️⃣ `diff`

Create two files:

```bash
echo "hello" > a.txt
echo "hello world" > b.txt
diff a.txt b.txt
```

---

# 📦 4. Compression & Archives

---

## 1️⃣ `tar`

Create archive:

```bash
tar -cvf archive.tar linux_practice
```

Extract:

```bash
tar -xvf archive.tar
```

---

## 2️⃣ `gzip`

```bash
gzip file1.txt
```

Decompress:

```bash
gunzip file1.txt.gz
```

---

## 3️⃣ `zip`

```bash
zip files.zip file1.txt
```

Unzip:

```bash
unzip files.zip
```

---

# 👤 5. Users & Permissions

---

## 1️⃣ `whoami`

```bash
whoami
```

---

## 2️⃣ `chmod`
chmod stands for change mode. 
- It is a command used in Unix/Linux systems (like Linux and macOS) to change file and directory permissions.

- Permissions control who can read, write, or execute a file
Give execute permission:

```bash
chmod +x file1.txt
```

Numeric:

```bash
chmod 755 file1.txt
```
# 🔐 chmod Quick Reference

## Permission Values

| Permission | Symbol | Value |
|------------|--------|--------|
| Read       | r      | 4      |
| Write      | w      | 2      |
| Execute    | x      | 1      |

---

## Numeric Permission Breakdown

| Number | Calculation | Permission |
|--------|-------------|------------|
| 7 | 4+2+1 | rwx |
| 6 | 4+2 | rw- |
| 5 | 4+1 | r-x |
| 4 | 4 | r-- |
| 0 | 0 | --- |

---

## Common chmod Commands

| Command | Resulting Permission | Description |
|----------|---------------------|-------------|
| `chmod +x file1.txt` | Adds execute permission | Adds `x` to all users |
| `chmod u+x file1.txt` | Owner gets execute | Adds `x` to owner only |
| `chmod 755 file1.txt` | rwxr-xr-x | Owner full access, others read & execute |
| `chmod 644 file1.txt` | rw-r--r-- | Owner read/write, others read only |
| `chmod 777 file1.txt` | rwxrwxrwx | Full access to everyone (⚠ not secure) |

---

## 755 Explained

| Category | Value | Permission |
|----------|--------|------------|
| Owner    | 7      | rwx |
| Group    | 5      | r-x |
| Others   | 5      | r-x |
---

## 3️⃣ `chown`

```bash
sudo chown $USER file1.txt
```

---

## 4️⃣ `sudo`

```bash
sudo apt update
```

---

# 💻 6. System Monitoring

---

## 1️⃣ `top`

```bash
top
```

Press `q` to exit.

---

## 2️⃣ `ps`

```bash
ps aux
```

---

## 3️⃣ `df`

```bash
df -h
```

---

## 4️⃣ `du`

```bash
du -h .
```

---

## 5️⃣ `free`

```bash
free -h
```

---

## 6️⃣ `uname`

```bash
uname -a
```

---

## 7️⃣ `history`

```bash
history
```

Run command again:

```bash
!10
```

---

# 🌐 7. Networking

---

## 1️⃣ `ping`

```bash
ping google.com
```

Stop with `CTRL+C`

---

## 2️⃣ `ip`

```bash
ip a
```

---

## 3️⃣ `curl`

```bash
curl https://example.com
```

---

## 4️⃣ `wget`

```bash
wget https://example.com
```

---

# ⚙️ 8. Process Management

---

## 1️⃣ Run background process

```bash
sleep 1000 &
```

Check:

```bash
ps aux | grep sleep
```

---

## 2️⃣ `kill`

```bash
kill <PID>
```

Force:

```bash
kill -9 <PID>
```

---

## 3️⃣ `pkill`

```bash
pkill sleep
```

---

# 📦 9. Package Management (WSL Ubuntu)

---

## Update system

```bash
sudo apt update
```

Upgrade:

```bash
sudo apt upgrade
```

Install package:

```bash
sudo apt install htop
```

---

# 📚 10. Help Commands

---

## `man`

```bash
man ls
```

Quit with `q`

---

## `whatis`

```bash
whatis ls
```

---

## `which`

```bash
which python
```

---

## `whereis`

```bash
whereis python
```

---