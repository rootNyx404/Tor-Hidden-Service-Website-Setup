# 🌐 Tor Hidden Service Website Setup (Educational Project)

## 📌 Overview

This project demonstrates how to host a local website using Apache and expose it through a Tor Hidden Service (.onion link).

👉 I successfully hosted the website and accessed it using **Tor Browser via the generated .onion link**.

> ⚠️ This project is strictly for educational purposes in a controlled lab environment.

---

## 🛠️ Technologies Used

* Linux (Kali / Parrot / Debian)
* Apache Web Server
* Tor Service
* HTML

---

## 🚀 Steps

### 1. Install Apache

```bash id="e3a1"
sudo apt install apache2 -y
```

### 2. Create Website Directory

```bash id="e3a2"
sudo mkdir -p /var/www/mywebsite
```

### 3. Configure Tor Hidden Service

Edit:

```bash id="e3a3"
/etc/tor/torrc
```

Add:

```id="e3a4"
HiddenServiceDir /var/lib/tor/hidden_service
HiddenServicePort 80 127.0.0.1:80
```

---

### 4. Restart Services

```bash id="e3a5"
sudo systemctl restart apache2
sudo systemctl restart tor
```

---

### 5. Get Onion Link

```bash id="e3a6"
sudo cat /var/lib/tor/hidden_service/hostname
```

---

## 🌍 Output

* Local Website: http://127.0.0.1
* Onion Website: generated .onion link
* Accessed successfully via Tor Browser

---

## ⚠️ Disclaimer

This project is for educational and lab use only.

---

## 👨‍💻 Author
  -Arup Halder

Your Name Here
