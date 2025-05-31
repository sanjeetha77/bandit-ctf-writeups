# **Bandit Level 21 → Level 22**

## **🧩 Challenge Description**

> A program is running automatically at regular intervals from cron, the time-based job scheduler.
> 
> 
> Look in `/etc/cron.d/` for the configuration and see what command is being executed.
> 

---

## 📘 Strategy

You need to:

1. Explore `/etc/cron.d/` for cron jobs.
2. Locate the cron job for **bandit22**.
3. Find the **script being executed**.
4. See if the script writes the password somewhere.
5. Read that location to get the **bandit22 password**.

---

## 🧠 Concept: How It Works

- A cron job is scheduled to run every minute as `bandit22`.
- It writes the **bandit22 password** to a file in `/tmp`.
- That file is **world-readable**, thanks to `chmod 644`.

---

# 🛠️ Commands Used

```bash
ls -la /etc/cron.d/
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t706lds9SORQqh9aMcz6ShpAoZKF7fgv
```

---

## ✅ Output
![WhatsApp Image 2025-05-31 at 10 50 49 PM](https://github.com/user-attachments/assets/667867d7-5393-4acf-a15c-0e61aad629a6)

---
