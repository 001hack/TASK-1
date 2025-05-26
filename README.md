# TASK-1
AIM : Scan Your Local Network for Open Ports

Objective: Learn to discover open ports on devices in your local network to understand network exposure.
Tools: Nmap (free), Wireshark (optional)

# 🔍 Local Network Port Scanning with Nmap

## 📌 Objective
Scan your local network to discover open ports and understand potential security exposures using **Nmap** and optionally **Wireshark**.

## ✅ Steps to Perform

### **Step 1 – Install Nmap**
- **Option 1**: Use **Kali Linux** (Nmap is pre-installed).
- **Option 2**: On Windows, download and install from [nmap.org](https://nmap.org/download.html).

---

### **Step 2 – Find Your Local IP Range**
- On **Windows**:
  1. Open Command Prompt.
  2. Run:
     ```bash
     ipconfig
     ```
  3. Note your IPv4 Address and Subnet Mask.
     - Example: `IPv4: 192.168.0.101` → Subnet: `192.168.0.0/24`

---

### **Step 3 – Run TCP SYN Scan**
In **Kali Linux Terminal**, run:
```bash
sudo nmap -sS 192.168.0.0/24
````

* Replace `192.168.0.0/24` with your network IP range if different.

---

### **Step 4 – Note IP Addresses and Open Ports**

* Review the output and write down:

  * IP addresses of active devices
  * Open ports and their services (e.g., 22/ssh, 80/http)

---

### **Step 5 – (Optional) Analyze with Wireshark**

* Open **Wireshark**
* Start capturing on your active interface
* Run your Nmap scan
* Use filters like:

  ```plaintext
  ip.addr == 192.168.0.X
  ```

---

### **Step 6 – Research Common Services**

Use Google or websites like:

* [speedguide.net](https://www.speedguide.net/ports.php)
* [SANS Port List](https://isc.sans.edu/port.html)

To understand what each port does and whether it should be open.

---

### **Step 7 – Identify Security Risks**

* Determine if services are:

  * Unnecessary
  * Outdated
  * Exposed to the internet
* Use security blogs or tools to check for known vulnerabilities.

---

### **Step 8 – Save Scan Results to File**

Save the output as a text file using:

```bash
sudo nmap -sS 192.168.0.0/24 -oN scan_result.txt
```

---

## 📁 Output Example

```
Nmap scan report for 192.168.0.1
PORT     STATE SERVICE
80/tcp   open  http

Nmap scan report for 192.168.0.101
PORT     STATE SERVICE
22/tcp   open  ssh
```

---

## 🛡️ Note

Always scan **only your own network**. Unauthorized scanning of other networks may be illegal.


