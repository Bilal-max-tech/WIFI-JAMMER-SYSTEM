* **Core Objective:** An educational and security research repository focused on analyzing IEEE 802.11 management frames, packet injection mechanics, and wireless defense strategies in C++.
* **Key C++ Modules & Architecture:**
* **Network Interface Controller:** Handles switching network cards into monitor mode via Netlink/`NL80211` APIs in Linux.
* **Packet Capture & Parsing:** Utilizes `libpcap` to capture raw 802.11 radiotap headers, MAC headers, and frame payloads.
* **Frame Construction Engine:** Defines raw C++ byte structures for 802.11 management frames (specifically subtype `0x000C` for Deauthentication).
* **Raw Socket Transmitter:** Utilizes low-level raw sockets (`AF_PACKET`, `SOCK_RAW`) to inject custom-crafted frames into the wireless spectrum.


* **Protocol Vulnerability Mechanism:**
* **Unauthenticated Frames:** Legacy 802.11 standards transmit management frames (such as Deauth and Disassociation) in plaintext without cryptographic authentication.
* **BSSID Spoofing:** Because sender MAC addresses are unverified in legacy frames, forged frames referencing a target Access Point or client force an immediate teardown of the wireless connection.


* **Detection & Defensive Countermeasures:**
* **IEEE 802.11w (PMF):** Implements Protected Management Frames, utilizing AES-128-CMAC to cryptographically sign management packets and render spoofed frames ineffective.
* **IDS/IPS Monitoring:** Analyzes sequence numbers, signal strength variance, and frame frequency anomalies in C++ to detect deauthentication floods.
* **WPA3 Standards:** Mandates PMF usage, eliminating deauthentication-based wireless disruption vulnerabilities on modern networks.


* **Legal & Regulatory Framework:**
* Transmission of unauthorized RF signals or spoofed management packets violates telecommunications laws (such as FCC regulations) and computer crime statutes. High-level analysis repositories restrict code execution to closed, self-contained laboratory environments or simulation frameworks.
