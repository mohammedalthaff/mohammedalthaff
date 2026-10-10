<h1 align="center">Mohammed Althaf</h1>

<p align="center">
  <b>Blue Team · SOC Analyst (Junior) · Detection and Monitoring</b><br>
  MSc Cybersecurity graduate · Dublin, Ireland
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/m-althaf"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:mohammadalthaf401@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## About

I build small detection labs and write up what they catch. My focus is the defender's side: collecting logs, writing detections, triaging alerts and automating the first response.

Open to **Junior SOC Analyst / Security Analyst** roles in Ireland.

## What I work on

- **SIEM and detection:** Wazuh, custom decoders and rules, alert triage
- **Network monitoring:** Suricata IDS/IPS, Filebeat log shipping, Wireshark
- **Threat analysis:** honeypots (Cowrie), attacker behaviour, indicators such as source IPs and file hashes
- **Automation:** Python and Bash for log monitoring and automated IP blocking
- **Attack simulation (lab only):** Nmap, Nikto, Hydra, SQL injection, to test whether my detections fire

## Featured projects

| Project | What it shows | Stack |
|---|---|---|
| [**Honeypot Deployment and Threat Analysis**](https://github.com/YOUR-USERNAME/honeypot-wazuh) | A Cowrie SSH honeypot feeding Wazuh. 1 custom decoder and 3 custom rules turn raw honeypot events into alerts for failed logins, commands run and file downloads (with SHA-256 hashes). | Cowrie, Wazuh, Hydra, Kali, VirtualBox |
| [**Network Security Monitoring with Wazuh and Suricata**](https://github.com/YOUR-USERNAME/wazuh-suricata-lab) | A 3-VM attack and defence lab. Nmap, Nikto, SQL injection and brute-force against DVWA are detected by Suricata and Wazuh, then a Python script blocks the attacker's IP. | Wazuh 4.7, Suricata, Filebeat, DVWA, iptables, Python |

## Example: a detection I wrote

Custom Wazuh rules for Cowrie honeypot events (from the honeypot project):

```xml
<group name="cowrie,">

  <rule id="100001" level="5">
    <decoded_as>json</decoded_as>
    <field name="eventid">cowrie.command.input</field>
    <description>Cowrie Honeypot: Command entered</description>
  </rule>

  <rule id="100002" level="5">
    <decoded_as>json</decoded_as>
    <field name="eventid">cowrie.login.failed</field>
    <description>Cowrie Honeypot: Failed login</description>
  </rule>

  <rule id="100003" level="7">
    <decoded_as>json</decoded_as>
    <field name="eventid">cowrie.session.file_download</field>
    <description>Cowrie Honeypot: File download</description>
  </rule>

</group>
```

Pipeline: `Cowrie JSON log → Wazuh agent → Wazuh manager → decoder and rules → dashboard alert`

## Next in the lab

- Correlation rule for multi-stage activity (brute force followed by a file download)
- Threat-intel and geolocation enrichment on honeypot alerts
- MITRE ATT&CK dashboards in Wazuh

## Tools

![Wazuh](https://img.shields.io/badge/Wazuh-005571?style=flat)
![Suricata](https://img.shields.io/badge/Suricata-EF3B2D?style=flat)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=flat&logo=wireshark&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali%20Linux-557C94?style=flat&logo=kalilinux&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat&logo=powershell&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=flat&logo=virtualbox&logoColor=white)

## Education and certifications

- MSc Cybersecurity, Dublin Business School (2025 - 2026)
- BCA (Information Technology), Malabar College of Arts and Science (2021 - 2024)
- Introduction to Cybersecurity, Cisco (2025)
- Deloitte Australia Cyber Job Simulation, Forage (2025)

## Get in touch

Email me at **mohammadalthaf401@gmail.com** or message me on LinkedIn.

<sub>All attack simulations in my repos run in isolated, host-only virtual labs that I own.</sub>
