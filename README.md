# 🔐 Linux Security Lab

> 🔥 Real-world SSH brute-force attack detection and mitigation using Fail2Ban

---

## 🚀 Overview (EN)

This project demonstrates real-world Linux security operations including SSH brute-force attack simulation, log analysis, and automated intrusion prevention.

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

bash id="f0l3y7" ssh fakeuser@<server-ip> 

### TR
Başarısız giriş logları oluşturmak için SSH brute-force saldırı denemeleri simüle edilmiştir.

bash id="3f7h2v" ssh fakeuser@<server-ip> 

---

## 🔍 Log Analysis

bash id="w6g8y1" sudo grep "Failed password" /var/log/auth.log 

Extract attacker IP addresses:

bash id="2j7m4s" sudo grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -nr 

### Example Output

bash id="9d1h3k" Failed password for invalid user fakeuser from 192.168.x.x port xxxx ssh2 

---

## 🛡️ Intrusion Prevention (Fail2Ban)

bash id="8p4k1q" sudo apt install fail2ban -y sudo systemctl start fail2ban sudo fail2ban-client status sshd 

### ⚙️ Fail2Ban Configuration

bash id="7m2z9c" [sshd] enabled = true port = 22 filter = sshd logpath = /var/log/auth.log maxretry = 5 bantime = 600 

### EN
Configured to automatically ban IPs after multiple failed attempts.

### TR
Belirli sayıda başarısız giriş sonrası IP’leri otomatik engelleyecek şekilde yapılandırıldı.

---

## 🌐 Network Scanning

bash id="3x9v8l" nmap -p 22,80,443 <target-ip> 

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

## 🔍 Log Analysis Example | Log Analizi Örneği

bash id="u3c8ax" cat /var/log/auth.log | grep "Failed password" 

---

## 📊 Suspicious Activity | Şüpheli Aktivite

bash id="4qz2y1" Failed password for invalid user admin from 192.168.1.101 port 22 ssh2 Failed password for root from 192.168.1.101 port 22 ssh2 

---

## 🧠 Detection Logic | Tespit Mantığı

### 🇬🇧 English
- Multiple failed SSH login attempts detected in /var/log/auth.log
- Repeated authentication failures from the same source IP address
- Pattern indicates a potential brute force attack
- Behavior flagged for further defensive action

### 🇹🇷 Türkçe
- /var/log/auth.log içinde çoklu başarısız SSH giriş denemeleri tespit edildi
- Aynı IP adresinden tekrar eden başarısız girişler gözlemlendi
- Bu davranış brute force saldırı ihtimalini göstermektedir
- İleri savunma aksiyonları için işaretlendi

---

## 🎯 Outcome | Sonuç

### 🇬🇧 English
- Suspicious IP successfully identified
- Attack pattern recognized through log analysis
- System prepared for defensive response (e.g., Fail2Ban)

### 🇹🇷 Türkçe
- Şüpheli IP başarıyla tespit edildi
- Log analizi ile saldırı paterni belirlendi
- Sistem savunma aksiyonlarına hazır hale getirildi (örneğin Fail2Ban)

---

## 🧠 Project Value | Proje Değeri

### 🇬🇧 English
This project demonstrates:
- Practical log analysis skills
- Threat detection using system logs
- Understanding of attack patterns
- Security monitoring mindset

### 🇹🇷 Türkçe
Bu proje aşağıdaki konularda yetkinlik kazandırır:
- Pratik log analizi becerisi
- Sistem logları ile tehdit tespiti
- Saldırı paternlerini anlama
- Güvenlik izleme bakışı

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

## ⚠️ Limitations

### EN
- Simulation performed in a controlled lab environment  
- Limited to SSH-based attacks  
- Not a full SIEM solution  

### TR
- Kontrollü bir lab ortamında yapılmıştır  
- Sadece SSH saldırılarına odaklanır  
- Tam kapsamlı bir SIEM çözümü değildir  

---

## 🚀 Future Improvements

### EN
- Integrate real-time log monitoring and alerting  
- Develop a Python-based log parser  
- Expand detection to web-based attacks  

### TR
- Gerçek zamanlı log izleme ve alarm sistemi ekleme  
- Python ile log analiz scripti geliştirme  
- Web saldırılarını kapsayacak şekilde genişletme  

---

## 🔗 Project Link

GitHub: https://github.com/murattkarateke/linux-security-lab

---

## 👤 Author

**Murat Karateke
