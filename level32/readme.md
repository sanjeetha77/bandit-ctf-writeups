# **Bandit Level 32 → Level 33**

---

## **🧩 Challenge Description**

After all this `git` stuff, it’s time for another escape. Good luck!

---

## Explanation

This level introduces a **custom restricted shell** that limits your command input. By calling `$0`, which is a shortcut to invoke the current shell binary, you can **escape** this restriction and return to a **normal bash shell**. Once escaped, you can execute usual commands freely and read the password file.

The presence of a **setuid binary** (`uppershell`) indicates elevated privileges for the next user (bandit33), making this technique essential.

---

# 🛠️ Commands Used

```bash
1. You are limited to uppercase commands, so a typical ls, cat, or even bash will throw an error.

However, we can bypass this restriction by using a trick:
Enter the command:
$0
$0 executes the default shell. In this case, it brings you into a normal shell.

2. Once you're in the normal shell, run:

ls -la
You’ll find a file named uppershell, owned by bandit33, and having the s (setuid) bit set.

3. Now simply run:

cat /etc/bandit_pass/bandit33
```

---

## ✅ Output

---