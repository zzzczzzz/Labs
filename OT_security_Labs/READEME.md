# Cybersecurity for Operational Technology

This repository showcases hands-on labs simulating real-world cyber attacks against industrial control systems and operational technology environments. These exercises explore weaknesses in PLCs, SCADA systems, industrial protocols, and firewall defenses.

## Key Labs and Evidence Files

1. **PLC and HMI Coil Manipulation via SCADA System**
   - Simulated unauthorized manipulation of Programmable Logic Controller coil values using a SCADA-connected HMI.
   - Attack altered motor ON/OFF states by modifying coil registers via exposed web interfaces.
   - Tools: SCADAbr, browser-based HMI, coil register controller, virtual PLC.
   - Impact: Demonstrated how insecure HMI interfaces can allow attackers to tamper with physical processes without authentication.
   - [View Report](./pdf_files/plc_hmi_manipulation.pdf)

2. **ARP Spoofing and Man-in-the-Middle in OT Networks**
   - Performed ARP spoofing using Kali Linux to hijack traffic between SCADA system and PLC.
   - Captured, observed, and manipulated live Modbus packets flowing through the network.
   - Tools: `arpspoof`, Wireshark, `ettercap`, Modbus simulator.
   - Impact: Showed how weak Layer 2 security in flat OT networks enables traffic interception and manipulation.
   - [View Report](./pdf_files/arp_spoofing_ot.pdf)

3. **Modbus Protocol Exploitation**
   - Analyzed unencrypted Modbus traffic and sent unauthorized `write_coil` commands to the PLC.
   - Aimed to change actuator behavior and disrupt control system logic.
   - Tools: `Modpoll`, Wireshark, custom command injection scripts.
   - Impact: Highlighted risks of running legacy ICS protocols like Modbus TCP without authentication or encryption.
   - [View Report](./pdf_files/modbus_exploitation.pdf)

4. **pfSense Firewall Configuration for OT Defense**
   - Configured firewall rules in pfSense to restrict access to the SCADA/PLC subnet.
   - Tested port filtering, IP-based blocking, and traffic segmentation.
   - Tools: pfSense firewall appliance, OT network topology, simulated attacks.
   - Impact: Demonstrated how segmentation and proper firewall rules prevent unauthorized access and remote attacks in OT environments.
   - [View Report](./pdf_files/pfsense_firewall.pdf)

---

## Full Report

[Download Full CP3417 OT Lab Report (PDF)](./pdf_files/CP3417_OT_Full_Report.pdf)

---

## Key Learnings

- ICS protocols like Modbus are vulnerable by design when unencrypted.
- HMI and SCADA interfaces can be exploited if authentication is weak or missing.
- Layer 2 attacks like ARP spoofing are highly effective in flat OT networks.
- Proper segmentation and firewall rules are essential in mitigating cyber-physical threats.


