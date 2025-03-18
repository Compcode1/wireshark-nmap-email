This project analyzed **email transmission security using Nmap & Wireshark**, focusing on:
- **DNS resolution of Gmail’s mail servers**
- **TLS and QUIC encryption behavior**
- **Nmap scanning of Gmail’s SMTP/IMAP/POP3 servers**
- **IPv4 vs. IPv6 security settings**
- **Network security misconfigurations and potential attack vectors**

---

## **1️⃣ Key Findings**
### **🟢 DNS Resolution Analysis**
- Gmail’s mail server (`smtp.gmail.com`) resolved via DNS queries.
- The MacBook → Gmail resolution step was **not fully captured** due to network limitations.

### **🟢 Email Encryption: TLS vs. QUIC**
- Gmail’s web interface (browser-based) used **QUIC** encryption.
- Gmail’s mail servers (SMTP/IMAP) used **TLS 1.0, 1.1, 1.2, and 1.3**.
- **TLS 1.0 & 1.1 remain enabled, despite security deprecations**.

### **🟢 Nmap Scan of Gmail’s Mail Servers**
- **IPv4 and IPv6 scans revealed identical encryption settings.**
- **Legacy ciphers (3DES) were still present**, though unlikely used.
- **IPv6 was prioritized in our network, leading to an initial oversight in scanning.**

---

## **2️⃣ Lessons Learned**
✅ **Ensure Wireshark and Nmap scans are aligned to the correct IP version (IPv4 vs. IPv6).**  
✅ **QUIC vs. TLS differences impact visibility in packet captures.**  
✅ **Nmap confirms security policies that Wireshark cannot directly observe.**  
✅ **Capturing MacBook traffic from the Dell was not straightforward and would require a different setup.**  
