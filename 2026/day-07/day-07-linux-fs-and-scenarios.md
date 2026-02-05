# 🐧 Day 07 – Linux File System Hierarchy & Scenario Practice

---

## 📁 Part 1: Linux File System Hierarchy

### `/`
Root of the Linux file system. Everything starts here.

```bash
ls -l /
```

---

### `/home`
User home directories.

```bash
ls -l /home
```

---

### `/root`
Home directory of the root user.

```bash
ls -l /root
```

---

### `/etc`
Configuration files for system and services.

```bash
ls -l /etc | head
cat /etc/hostname
```

---

### `/var/log`
System and service log files.

```bash
ls -l /var/log | head
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

---

### `/tmp`
Temporary files.

```bash
ls -l /tmp
```

---

### `/bin`
Essential command binaries.

```bash
ls -l /bin | head
```

---

### `/usr/bin`
User-installed command binaries.

```bash
ls -l /usr/bin | head
```

---

### `/opt`
Optional third-party applications.

```bash
ls -l /opt
```

---

## 🧠 Part 2: Scenario Practice

### Scenario 1: Service Not Starting

```bash
systemctl status myapp
journalctl -u myapp -n 50
systemctl is-enabled myapp
systemctl list-units --type=service | grep myapp
```

---

### Scenario 2: High CPU Usage

```bash
top
ps aux --sort=-%cpu | head -10
```

---

### Scenario 3: Finding Service Logs

```bash
systemctl status docker
journalctl -u docker -n 50
journalctl -u docker -f
```

---

### Scenario 4: File Permission Issue

```bash
ls -l /home/user/backup.sh
chmod +x /home/user/backup.sh
./backup.sh
```

---

## ✅ What I Learned

- Where important Linux directories are
- How to find logs and config files
- How to troubleshoot services, CPU issues, logs, and permissions
