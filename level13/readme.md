# Bandit Level 12 → Level 13

## **🧩** Challenge Description

The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed. For this level, it may be useful to create a directory under `/tmp` in which you can work.

---

## Explanation

- To begin, it’s best practice to create a working directory inside `/tmp` so that all operations can be safely performed without cluttering your home directory. This can be done using `mkdir /tmp/bandit12` followed by `cd /tmp/bandit12`. Next, copy the original `data.txt` file from the home directory to your working folder using `cp ~/data.txt .`.
- Once the file is copied, the first step is to reverse the hexdump using the command `xxd -r data.txt revert.txt`. This command converts the ASCII hexadecimal representation back into its original binary form. Now that you have a binary file (`revert.txt`), you need to determine what kind of file it is. For that, use the `file revert.txt` command. This utility examines the file signature and tells you what type of compression or format the file is in.
- Based on the output from the `file` command, rename the file to match the expected extension. For instance, if `file` reports that the content is a gzip archive, rename it using `mv revert.txt revert.gz`, then decompress it with `gzip -d revert.gz`. This will yield a new file named `revert`. Again, use `file revert` to determine the next format. If it reports bzip2 compression, rename the file to `revert.bz2` and decompress it using `bzip2 -d revert.bz2`.
- This process continues, often going through gzip, bzip2, and tar formats multiple times. When the file type reported is a tar archive (a file containing other files), you can extract its contents using `tar -xf filename.tar`. As you extract new files, repeat the process of checking their type with `file`, renaming them appropriately, and decompressing or extracting them with the correct tool.
- Eventually, after repeating this process several times, you will reach a plain text file. You can verify this when the `file` command reports something like "ASCII text." At that point, simply use `cat filename` (e.g., `cat data8`) to display the contents of the file, which will reveal the password needed to progress to Level 13.

---

## Strategy

1. Reverse the hexdump using `xxd -r`.
2. Detect file type using `file`.
3. Rename accordingly and decompress using tools like `gzip`, `bzip2`, and `tar`.
4. Repeat until you reach the final text output.

---

## 🛠️ Tools Used

- `xxd` – to reverse the hex dump
- `file` – to identify the file type
- `mv` – to rename files based on detected format
- `gzip`, `bzip2`, `tar` – to decompress the files

## 🖥️ Commands Used

```bash
# Step 1: Create a temp directory and move into it
mkdir /tmp/bandit12
cd /tmp/bandit12

# 2. Copy the file
cp ~/data.txt .
xxd -r data.txt revert.txt

# 3. Keep checking the file type and decompress
file revert.txt      # output says gzip
mv revert.txt revert.gz
gzip -d revert.gz    # now becomes 'revert'

file revert          # output: bzip2
mv revert revert.bz2
bzip2 -d revert.bz2

file revert          # output: gzip
mv revert revert.gz
gzip -d revert.gz

file revert          # output: POSIX tar
mv revert revert.tar
tar -xf revert.tar

# 4. Keep repeating decompression:
# Check file > rename > decompress > extract if tar

file data5.bin       # tar archive
mv data5.bin data5.tar
tar -xf data5.tar

file data6.bin       # tar archive
mv data6.bin data6.tar
tar -xf data6.tar

file data8.bin       # gzip
mv data8.bin data8.gz
gzip -d data8.gz

# 5. Final step: check the content
cat data8

```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/7f44bc39-c104-46f3-9e41-f238e7646436)
![image](https://github.com/user-attachments/assets/1c53ad52-60e0-4ecf-b340-ad74e222aad1)
![image](https://github.com/user-attachments/assets/9aeefc6e-33a9-4ad6-9926-87f31f14b885)

---
