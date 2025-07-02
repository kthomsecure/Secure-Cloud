# osTicket Lab Installation Log

This repository documents the troubleshooting and successful deployment of osTicket inside a Windows-based virtual machine hosted in Azure. The goal of this project was to simulate a practical help desk ticketing system configuration while navigating IIS, PHP, and firewall rules—demonstrating applied IT support and system admin skills.

---

## ✅ Lab Goal

Install and configure osTicket on a Windows Server VM in Azure using IIS, PHP, and MySQL. Resolve common configuration issues along the way to gain real-world troubleshooting experience.

---

## 🔧 Environment

- **Virtual Machine:** Windows Server (Azure-hosted)
- **Web Server:** IIS 10
- **PHP Version:** 7.3.8
- **Database:** MySQL
- **Firewall:** Azure Network Security Group (NSG)
- **Browser:** Edge (localhost testing)
- **Local system:** macOS (host system using RDP)

---

## 🔍 Issues Encountered & Resolved

### 1. **HTTP Error 500.19**
- **Cause:** Invalid or malformed `web.config` file.
- **Fix:** Renamed corrupted or default file to `web.config.old` and allowed osTicket to recreate it properly.

### 2. **Handler Mapping Issue**
- **Cause:** Missing PHP handler for `.php` files in IIS.
- **Fix:** Used IIS Manager to confirm and restore `php-7.3.8` handler mappings using `FastCgiModule`.

### 3. **Firewall Block**
- **Cause:** Port 80 was not reachable from browser.
- **Fix:** Checked Azure NSG rules to ensure `Allow-HTTP` (port 80) was set to "Allow" for inbound traffic.

### 4. **Configuration File Missing**
- **Cause:** osTicket reported missing `ost-config.php`.
- **Fix:** Renamed `include/ost-sampleconfig.php` to `include/ost-config.php`.

---

## 🧠 Skills Demonstrated

- IIS Configuration (bindings, handler mappings)
- Azure Network Security Group rule creation
- File system navigation and permission fixes
- PHP extension troubleshooting
- Firewall diagnostics (localhost and external)
- Debugging `HTTP 500.19` errors and XML parsing issues
- Using PowerShell and File Explorer to apply server changes

---

## 📁 Directory Reference

- IIS Root: `C:\inetpub\wwwroot\osTicket`
- osTicket Config: `include/ost-config.php`

---

## 📅 Completion Date

**July 02, 2025**

---

## 🤝 Author

Kevin Thomas  
Technology Support Specialist | Security+ Certified  
GitHub: [@kthomsecure)  
