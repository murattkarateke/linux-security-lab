# 🔐 Linux Security Lab

> 🔥 Real-world SSH brute-force attack detection and mitigation using Fail2Ban

---

## 🚀 Overview (EN)

This project demonstrates real-world Linux security operations, including SSH brute-force attack simulation, log analysis, and automated intrusion prevention.

The lab replicates attacker behavior and shows how to detect, analyze, and mitigate unauthorized access using industry-standard tools.

---

## 🚀 Proje Özeti (TR)

Bu proje, gerçek dünya senaryolarına yakın şekilde Linux güvenliği, SSH brute-force saldırı simülasyonu, log analizi ve otomatik saldırı engelleme süreçlerini göstermektedir.

Saldırgan davranışı simüle edilerek sistem üzerinde nasıl tespit ve önleme yapılacağı gösterilmiştir.

---

## 🏆 Key Achievements

- Detected multiple SSH brute-force attack attempts  
- Identified attacker IP addresses via log analysis  
- Implemented Fail2Ban to automatically block malicious IPs  
- Secured SSH access against unauthorized login attempts  

---

## 🏆 Öne Çıkan Başarılar

- SSH brute-force saldırıları başarıyla tespit edildi  
- Log analizi ile saldırgan IP adresleri belirlendi  
- Fail2Ban ile otomatik IP engelleme sistemi kuruldu  
- SSH erişimi güvenli hale getirildi  

---

## 🌍 Real World Impact

This project simulates real-world attack scenarios and demonstrates how system administrators detect and prevent unauthorized access on Linux servers.

---

## 🌍 Gerçek Dünya Etkisi

Bu proje, gerçek dünya saldırı senaryolarını simüle ederek Linux sunucularda yetkisiz erişimin nasıl tespit ve engellendiğini göstermektedir.

---

## 🛠️ Technologies Used

- Ubuntu Server (AWS EC2)  
- OpenSSH  
- Fail2Ban  
- Nmap  
- Linux CLI  

---

## 🧪 Lab Steps

1. Connected to remote Linux server via SSH  
2. Performed port scanning using Nmap  
3. Simulated brute-force login attempts  
4. Analyzed /var/log/auth.log for failed logins  
5. Extracted attacker IP addresses  
6. Configured Fail2Ban to block malicious activity  

---

## ⚔️ Attack Simulation

### EN
Brute-force SSH login attempts were simulated to generate failed login logs.

bash ssh fakeuser@<server-ip> 

### TR
Başarısız giriş logları oluşturmak için SSH brute-force saldırı denemeleri simüle edilmiştir.

bash id="cyr63y" ssh fakeuser@<server-ip> 

---

## 🔍 Log Analysis

bash id="n9o6a3" sudo grep "Failed password" /var/log/auth.log 

Extract attacker IP addresses:

bash id="b3x8lc" sudo grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -nr 

### Example Output

bash id="gxh0e8" Failed password for invalid user fakeuser from 192.168.x.x port xxxx ssh2 

---

## 🛡️ Intrusion Prevention (Fail2Ban)

bash id="s3b1x4" sudo apt install fail2ban -y sudo systemctl start fail2ban sudo fail2ban-client status sshd 

### ⚙️ Fail2Ban Configuration

bash id="7t4gph" [sshd] enabled = true port = 22 filter = sshd logpath = /var/log/auth.log maxretry = 5 bantime = 600 

### EN
Configured to automatically ban IPs after multiple failed attempts.

### TR
Belirli sayıda başarısız giriş sonrası IP’leri otomatik engelleyecek şekilde yapılandırıldı.

---

## 🌐 Network Scanning

bash id="k1zv3y" nmap -p 22,80,443 <target-ip> 

---

## 📊 Results

### EN
- 30+ failed login attempts detected  
- Multiple attacker IP addresses identified  
- 8 IP addresses automatically banned  

### TR
- 30+ başarısız giriş denemesi tespit edildi  
- Birden fazla saldırgan IP adresi belirlendi  
- 8 IP otomatik olarak engellendi  

---

## 📸 Screenshots

These screenshots provide evidence of real-world attack simulation and defense mechanisms.

Bu ekran görüntüleri gerçek dünya saldırı simülasyonu ve savunma mekanizmalarını göstermektedir.

### 🔐 SSH Connection
SSH Connection

### 🌐 Nmap Scan
Nmap Scan

### 🚨 Attack Logs
Attack Logs

### 🛡️ Fail2Ban Protection
Fail2Ban

---

## 🧠 Skills Gained

### EN
- Log analysis and investigation  
- SSH security hardening  
- Intrusion detection and prevention  
- Blue Team fundamentals  

### TR
- Log analizi ve inceleme  
- SSH güvenliği  
- Saldırı tespiti ve engelleme  
- Blue Team temelleri  

---

## 📌 Why This Project Matters (EN)

This project demonstrates practical SOC / Blue Team skills including incident detection, log investigation, and threat mitigation.

---

## 📌 Bu Proje Neden Önemli (TR)

Bu proje gerçek dünya güvenlik becerlerini gösterir: olay tespiti, log analizi ve tehdit engelleme.

---

## 👤 Author

**Murat Karateke
