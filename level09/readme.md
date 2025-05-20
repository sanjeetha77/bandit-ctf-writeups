# Bandit Level 8 → Level 9

## **🧩** Challenge Description

The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.

---

## **🛠** Commands You Might Use

- `ls -la` – list all files with permissions
- `sort` – sort lines of text
- `uniq -u` – filter and print only unique lines
- `cat` – read and print file contents
- `man <cmd>` – show manual for any command (e.g., `man uniq`)

---

## **💻** Steps and Commands Used

```bash
# Step 1: Confirm the file is present
ls -la

# Step 2: Sort the contents of the file and filter out unique line
sort data.txt | uniq -u

```

## Additional Tip

You can use `man uniq` to see useful flags like:

- `u` : only print unique lines (appear exactly once)

## ✅ Output

---