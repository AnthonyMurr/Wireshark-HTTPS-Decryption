# Wireshark-Training
Collection of Wireshark resources &amp; PCAP files used in the Blue Team training course

# Note
- The zipped Dridex PCAP archive is password protected, to unencrypt it, use the password "infected"

---

# Wireshark HTTPS Decryption - Installation & Usage Guide

This guide will walk you through setting up Wireshark to decrypt HTTPS/SSL/TLS traffic using the provided PCAP file and keys log file.

## Prerequisites

- **Wireshark** installed on your system
  - Download from [wireshark.org](https://www.wireshark.org/download.html) if you don't have it installed

## Step 1: Configure Wireshark to Use the Keys Log File

1. Open Wireshark
2. Go to **Edit → Preferences** (or **Wireshark → Preferences** on Mac)
3. Navigate to **Protocols → TLS** (or **Protocols → SSL** in older versions)
4. In the **(Pre)-Master-Secret log filename** field, browse and select:
   ```
   Wireshark-tutorial-KeysLogFile.txt
   ```
5. Click **OK** to save

## Step 2: Open the PCAP File

1. In Wireshark, go to **File → Open**
2. Navigate to and select:
   ```
   Wireshark-tutorial-on-decrypting-HTTPS-SSL-TLS-traffic.pcap
   ```
3. Click **Open**

## Step 3: View Decrypted Traffic

Once the PCAP is loaded:
- The HTTPS/SSL/TLS traffic should be automatically decrypted using the keys from the log file
- You can see the decrypted HTTP data in the packet details
- Right-click on a packet → **Follow → HTTP Stream** to see the full conversation



## Note

The keys log file (`Wireshark-tutorial-KeysLogFile.txt`) contains the session keys in NSS Key Log Format, which allows Wireshark to decrypt the captured traffic.

---


# What is This Good For?

This Wireshark training resource is valuable for several practical applications:

## 1. Security Analysis & Incident Response

- **Malware Analysis**: Decrypt HTTPS traffic to see what malware is communicating with command-and-control servers
- **Threat Hunting**: Inspect encrypted connections for suspicious activity
- **Forensics**: Analyze network traffic during security incidents to understand what happened

## 2. Network Troubleshooting

- **Debug HTTPS Issues**: See actual HTTP requests/responses when debugging web applications
- **API Debugging**: Inspect API calls and responses in encrypted connections
- **Performance Analysis**: Identify bottlenecks in encrypted traffic

## 3. Security Training & Education

- **Blue Team Training**: Learn network forensics and traffic analysis techniques
- **Understanding Encryption**: See how SSL/TLS works in practice
- **Traffic Inspection**: Learn to analyze encrypted protocols

## 4. Application Development

- **Testing**: Verify that your applications send/receive data correctly over HTTPS
- **Security Validation**: Ensure sensitive data is properly encrypted
- **Protocol Analysis**: Understand how your app communicates with servers

## 5. Compliance & Auditing

- **Traffic Inspection**: Verify compliance with security policies
- **Data Flow Analysis**: Track how sensitive data moves through encrypted channels

## Real-World Scenario Example

If you suspect malware on a network:
1. Capture traffic with Wireshark
2. Use the keys log file (if you have access to the client's session keys)
3. Decrypt the HTTPS traffic
4. See what data is being exfiltrated or what commands are being received

This is a practical skill for cybersecurity professionals, network administrators, and developers working with encrypted protocols.

---


