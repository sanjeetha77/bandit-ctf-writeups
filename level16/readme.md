# Bandit Level 15 → Level 16

## **🧩** Challenge Description

> The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
> 

---

## Explanation

- You're asked to communicate with a service running on port `30001` that expects an encrypted (SSL/TLS) connection.
- Instead of regular `nc`, you must use `ncat` or `openssl s_client`, both of which support SSL/TLS.

---

## 🖥️ Commands Used

```bash
Syntax:
ncat <host> <port> 
ncat localhost 30001 --ssl
```

---

## ✅ Output

---