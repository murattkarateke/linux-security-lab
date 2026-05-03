# 🔐 Linux Security Lab

---

## 🚀 Overview (EN)

This project demonstrates real-world Linux security operations including SSH log analysis, brute-force attack detection, and automated intrusion prevention.

The lab simulates attacker behavior and shows how to detect and mitigate it using industry-standard tools.

---

## 🚀 Proje Özeti (TR)

Bu proje, gerçek dünyaya yakın senaryolarla Linux güvenliği, SSH log analizi ve saldırı tespiti üzerine yapılmıştır.

Saldırgan davranışı simüle edilerek sistemde nasıl tespit ve engelleme yapılacağı gösterilmiştir.

---

## 🧠 Key Skills / Kazanılan Beceriler

### EN
- Log Analysis (auth.log)
- Brute-force Attack Detection
- Attacker IP Extraction
- Intrusion Prevention (Fail2Ban)
- Network Scanning (Nmap)
- Linux System Hardening

### TR
- Log analizi (auth.log)
- Brute-force saldırı tespiti
- Saldırgan IP adresi çıkarma
- Fail2Ban ile saldırı engelleme
- Nmap ile port tarama
- Linux sistem güvenliği

---

## ⚔️ Attack Simulation (EN)

Simulated unauthorized SSH login attempts:

bash ssh fakeuser@<server-ip> 

### Result:
- Multiple failed login attempts generated
- Logged in /var/log/auth.log
- Detected and analyzed successfully

---

## ⚔️ Saldırı Simülasyonu (TR)

Yetkisiz SSH giriş denemeleri simüle edildi:

bash ssh fakeuser@<server-ip> 

### Sonuç:
- Birden fazla başarısız giriş denemesi üretildi
- /var/log/auth.log içine kaydedildi
- Başarıyla analiz edildi

---

## 🔍 Log Analysis (EN)

bash sudo grep "Failed password" /var/log/auth.log 

Extract attacker IPs:

bash sudo grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -nr 

---

## 🔍 Log Analizi (TR)

bash sudo grep "Failed password" /var/log/auth.log 

Saldırgan IP adreslerini çıkarma:

bash sudo grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -nr 

---

## 🛡️ Intrusion Prevention (Fail2Ban)

bash sudo apt install fail2ban -y sudo systemctl start fail2ban sudo fail2ban-client status sshd 

### Result:
- Malicious IPs automatically banned
- Real-time protection enabled

---

## 🛡️ Saldırı Engelleme (Fail2Ban)

bash sudo apt install fail2ban -y sudo systemctl start fail2ban sudo fail2ban-client status sshd 

### Sonuç:
- Zararlı IP’ler otomatik engellendi
- Gerçek zamanlı koruma sağlandı

---

## 🌐 Network Scanning (EN)

bash nmap -p 22,80,443 <target-ip> 

### Result:
- Open ports detected
- Attack surface analyzed

---

## 🌐 Ağ Taraması (TR)

bash nmap -p 22,80,443 <target-ip> 

### Sonuç:
- Açık portlar tespit edildi
- Sistem yüzeyi analiz edildi

---

## 📸 Screenshots

### SSH Attack Logs
ssh-log

### Fail2Ban Protection
fail2ban

---

## 📊 Results / Sonuçlar

### EN
- 30+ failed login attempts detected  
- Multiple attacker IPs identified  
- 8 IP addresses automatically banned  

### TR
- 30+ başarısız giriş denemesi tespit edildi  
- Saldırgan IP adresleri çıkarıldı  
- 8 IP otomatik olarak engellendi  

---

## 🧰 Technologies Used

- Ubuntu Server  
- SSH  
- Fail2Ban  
- Nmap  
- Linux CLI  

---

## 🎯 Why This Project Matters (EN)

This project demonstrates real-world SOC / Blue Team skills, including:

- Incident detection  
- Log investigation  
- Threat mitigation  

---

## 🎯 Bu Proje Neden Önemli (TR)

Bu proje aşağıdaki gerçek dünya becerilerini gösterir:

- Olay tespiti  
- Log analizi  
- Tehdit engelleme  

---

## 👤 Author

**Murat Karatek
