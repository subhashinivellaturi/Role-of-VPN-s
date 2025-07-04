# 🔒 VPN Privacy and Security Task – Cyber Security Internship

## 🎯 Objective
Understand the role of VPNs in protecting privacy and ensuring secure online communication by setting up and testing a free VPN client.

---

## 🧰 Tools Used
- **Kali Linux (VirtualBox VM)**
- **ProtonVPN (Free Tier)**
- **OpenVPN**
- **Firefox Browser**
- **Command-line tools:** curl, openvpn

---

## ✅ Steps Performed

### 1️⃣ Choose a reputable free VPN service and sign up  
Chose **ProtonVPN**, a well-known privacy-respecting VPN provider. Signed up for a **Free Tier** account at [https://protonvpn.com](https://protonvpn.com).

---

### 2️⃣ Download and install the VPN client  
Since ProtonVPN CLI is deprecated, used **OpenVPN** as the client. Installed using:

```bash
sudo apt install openvpn -y
```
Downloaded OpenVPN configuration files (.ovpn) for free servers from the official ProtonVPN dashboard.

---

3️⃣ Connect to a VPN server
Used the following command to connect to the downloaded .ovpn config file:
```bash
sudo openvpn --config ~/Downloads/us-free-104.protonvpn.udp.ovpn
```
Entered OpenVPN username and password from ProtonVPN account settings.

✅ VPN connected successfully with message:
Initialization Sequence Completed

4️⃣ Verify your IP address has changed
Used the following to confirm IP change:

```bash

curl ifconfig.me
```
Also verified on https://whatismyipaddress.com

➡️ New IP matched VPN server location (USA).

5️⃣ Browse a website to confirm traffic is encrypted
Used Firefox to access multiple websites while connected. All data tunneled securely through VPN (encrypted).

6️⃣ Disconnect VPN and compare browsing speed and IP
Disconnected the VPN (Ctrl+C) and repeated:

``` bash

curl ifconfig.me
```
Confirmed IP returned to original ISP IP.
Browsing speed was slightly faster when VPN was off (as expected).

7️⃣ Research VPN encryption and privacy features
Encryption: OpenVPN uses AES-256-bit encryption, which is military grade.

Privacy: VPN hides real IP and location, prevents ISP tracking, and protects data on public Wi-Fi.

ProtonVPN also has a no-logs policy, meaning it doesn’t store user activity.

8️⃣ Summary of VPN Benefits and Limitations
✅ Benefits:
Encrypts all outgoing/incoming traffic

Hides real IP address

Bypasses geo-restrictions and censorship

Protects privacy on public networks

⚠️ Limitations:
- Slight speed reduction due to encryption overhead
- Some sites block VPN IPs
- Free plans have limited server options and slower speeds

📝 Conclusion
Using ProtonVPN with OpenVPN on Kali Linux demonstrated how VPNs effectively secure network traffic and protect user identity. This setup is essential for cybersecurity professionals who work on sensitive networks or use public Wi-Fi.
