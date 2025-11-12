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

## What You'll Learn

- How to decrypt HTTPS traffic in Wireshark using pre-master secret keys
- Analyzing encrypted network traffic
- Understanding SSL/TLS handshakes and encrypted data flows

## Note

The keys log file (`Wireshark-tutorial-KeysLogFile.txt`) contains the session keys in NSS Key Log Format, which allows Wireshark to decrypt the captured traffic.

---

**Need help?** Check out the main README.md or refer to Wireshark's official documentation.

