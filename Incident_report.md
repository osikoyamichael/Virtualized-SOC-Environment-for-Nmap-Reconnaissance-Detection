# Incident Repsonse Report   
## Firewall Reconnaissance Detection 

### 1. Executive Summary 
On march 1, 2026, Mutilple blocked TCP SYN attempts were detect against ubuntu server( 192.168.56.102).Activity indicates active network emuration consistent with Nmap SYN scanning.

### 2. Timeline 
- Mutiple TCP SYN packets observed
- Firewall blocked repeated attempts
- splunk detection

### 3. Evidence 
Mar  1 20:04:17 archangel kernel: [  540.273669] [UFW BLOCK] IN=enp0s3 OUT= MAC=08:00:27:7d:4a:11:0...... SRC=192.168.56.102 DST=192.168.56.101 LEN=52 TOS=0x00 PREC=0x00 TTL=128 ID=24850 DF PROTO=TCP SPT=61633 DPT=8001 WINDOW=65535 RES=0x00 SYN URGP=0 
host = archangel source = /var/log/ufw.logsourcetype = syslog

### 4. Analysis
- TCP protocol
- SYN flag only (no handshake completion)
- Repeated attemts from same source (IP)
- Mutiple ports targeted

### 5. MITRE ATT&CK Mapping 
Discovery Active scanning (T1595)

### 6. Risk Assessment 
Risk level: Medium

Impact: Low (blocked successfully by Firewall)

### 7. Recommendations 
- Maintain firewall configuration
- Monitor repeated scanning behavior and set alert. 
- Implement IDS (e.g., snort)
- Restrict exposed services.
