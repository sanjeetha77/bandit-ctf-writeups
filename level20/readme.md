# **Bandit Level 20 → Level 21**

## **🧩 Challenge Description**

> There's a setuid binary called suconnect in the home directory.
> 
> 
> It connects to `localhost` on a port **you provide** and waits for a line of text (a password).
> 
> If the input **matches** the password of **bandit20**, it returns the password for **bandit21**.
> 

---

## 📘 Strategy

You need to:

1. **Run a local server** (using `netcat`) that listens on a port.
2. **Send the bandit20 password** through this connection.
3. Use `./suconnect <port>` to connect to that server.
4. If the password matches, it returns **bandit21's password**.

---

## 🧠 Concept: How It Works

- You act like a server (using `netcat`).
- `suconnect` connects to your server and reads what you send.
- If your input equals the **bandit20 password**, it returns the **bandit21 password**.

---

## 🛠️ Commands Used

```bash
ls -la
echo "<bandit20_password>" | netcat -lp 1234 &
./suconnect 1234
```

---

## Step-by-Step Explanation

1. `ls -la`
    
    Shows a setuid file named `suconnect`.
    
2. `echo "0qXahGBZJv0MN9Ghs7iOWsCfZyxOUbYO" | netcat -lp 1234 &`
    
    Starts a **background server** that sends the bandit20 password on port `1234`.
    
3. `./suconnect 1234`
    
    The binary connects to `localhost:1234`, reads the line sent, checks if it’s the correct password, and prints the **next level’s password**.
    

---

## ✅ Output

---