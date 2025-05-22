# Bandit Level 14 → Level 15

## **🧩** Challenge Description

The password for the next level can be retrieved by submitting the password of the current level to port `30000` on `localhost`.

---

## Explanation

- Once you have logged into the `bandit14` user (from the previous level using the private SSH key), you need to communicate with a service running locally on port `30000`.
- This can be done using the `nc` (netcat) command, which is a networking utility used for reading or writing data across network connections using TCP or UDP.
- To send the current level’s password to the service, you just have to pass it as input to `nc localhost 30000`.
- If the password is correct, the service will respond with the password for the next level.

---

## Strategy

1. Log in to `bandit14`.
2. Use `nc localhost 30000`.
3. Input the current password to receive the next level's password.

---

## 🛠️ Tools Used

- `ssh` – to log in
- `nc` – to communicate with a local TCP service

---

## 🖥️ Commands Used

```bash

# Step 1: Use netcat to send password to port 30000
nc localhost 30000
MU4WWeTyJk8R0oif1qqmcBPAlh7LDC PvS
Correct!
```

---

## ✅ Output

---