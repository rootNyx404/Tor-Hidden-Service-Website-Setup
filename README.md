# 🌐 Tor Hidden Service Website Setup (Full A to Z Guide)

## 📌 Overview

This project explains step-by-step how to:

- Install and use Tor Browser  
- Host a local website using Apache  
- Expose it as a Tor Hidden Service (.onion site)  
- Access it securely via the Tor network  

👉 I successfully hosted the website and accessed it using a generated .onion link.

⚠️ This project is strictly for educational purposes in a controlled lab environment.

---

## 🛠️ Step 1: Install Tor Browser

### 🔽 Download Tor Browser
Download from official site:  
https://www.torproject.org/download/

### 📦 Install (Linux example)
```bash
tar -xvf tor-browser-linux*.tar.xz
cd tor-browser
./start-tor-browser.desktop
🛠️ Step 2: Install Apache Web Server
sudo apt update
sudo apt install apache2 -y
🛠️ Step 3: Create Website
sudo mkdir -p /var/www/mywebsite

Create homepage:

sudo nano /var/www/mywebsite/index.html

Paste:

<html>
  <body>
    <h1>Hello! My Tor Hidden Website 🚀</h1>
  </body>
</html>
Give feedback
🛠️ Step 4: Configure Apache
sudo nano /etc/apache2/sites-enabled/000-default.conf

Change:

DocumentRoot /var/www/mywebsite

Restart:

sudo systemctl restart apache2
🛠️ Step 5: Install Tor Service
sudo apt install tor -y
🛠️ Step 6: Configure Tor Hidden Service

Edit config:

sudo nano /etc/tor/torrc

Add:

HiddenServiceDir /var/lib/tor/hidden_service
HiddenServicePort 80 127.0.0.1:80
🔄 Step 7: Restart Tor
sudo systemctl restart tor
🔑 Step 8: Get .onion Link
sudo cat /var/lib/tor/hidden_service/hostname

Example output:

abcd1234xyz.onion
🌐 Step 9: Access Website

Open Tor Browser and visit:

http://your-generated-link.onion

✔ Your website is now live on Tor network

🌍 Output
Local Site: http://127.0.0.1
Onion Site: .onion link generated
Access: Only via Tor Browser
⚠️ Disclaimer

This project is for:

Educational purpose only
Cybersecurity learning lab
Controlled environment use
👨‍💻 Author
    -Arup Halder
