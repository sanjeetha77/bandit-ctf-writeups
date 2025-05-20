# Bandit Level 6 → Level 7

## 🧩 Challenge Description

The password for the next level is stored **somewhere on the server** and meets **all of the following conditions**:

- It is **owned by user `bandit7`**
- It is **owned by group `bandit6`**
- It is **exactly 33 bytes** in size

Once found, use the password to SSH into `bandit7` on port `2220`.

---

## 🛠 Commands You Might Use

- `find` – locate files based on user, group, size, permissions, etc.
- `cat` – view contents of a file
- `2>/dev/null` – suppress error messages (useful when searching system directories)
- `man find` – for learning all filter options for `find`

---

## 💻 Steps and Commands Used

```bash
# Step 1: Use find to search for files with specific user, group, and size
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

# Output:
/var/lib/dpkg/info/bandit7.password

# Step 2: Display the contents of the file to get the password
cat /var/lib/dpkg/info/bandit7.password

```

## ✅ Output

---