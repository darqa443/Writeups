# 🛡️ Wreath Penetration Test Report Summary

This summary documents the full penetration test methodology used to compromise the Wreath network, focusing on **network pivoting** and advanced post-exploitation techniques within a segmented Windows Active Directory environment.

**[View Full Penetration Test Report (PDF)](./Report-Wreath.pdf)**

---

## 🎯 Key Attack Vectors & Critical Findings

| Finding / Vector | Description (Demonstrated Skill) |
| :--- | :--- |
| **Remote Code Execution (RCE)** | Exploitation of two critical vulnerabilities: **MiniServ 1.890/Webmin RCE** and **GitStack 2.3.10 RCE** to gain initial footholds on public-facing assets. |
| **Network Pivoting** | Successfully bypassing network segmentation barriers to perform **Internal Network Enumeration** and reach the internal domain. |
| **Privilege Escalation** | Leveraging an **Unquoted Service Path** vulnerability on an internal host to achieve **SYSTEM**-level access. |
| **Post-Exploitation** | Dumping registry hives (**SAM/SYSTEM**) and using **secretsdump.py** (Impacket) to recover the NT hash of the local **Administrator** account. |
| **Exposed Assets** | Identified and utilized an **Exposed Private Key (id_rsa)** for lateral movement/access validation. |

## 🛠️ Methodological Summary (The Kill Chain)

1.  **External Access:** Gaining initial shell access via RCE vulnerabilities on two separate public web services.
2.  **Internal Reconnaissance:** Detailed scanning and mapping of the internal network, identifying Domain Controllers and key internal servers.
3.  **Lateral Movement:** Utilizing pivot techniques and collected credentials/keys to move across segmented network layers.
4.  **Privilege Escalation & Domain Access:** Exploiting system misconfigurations (Unquoted Service Path) to acquire SYSTEM privileges and finalize the compromise by extracting credential hashes.
5.  **Clean Up:** Removing artifacts, logs, and newly added firewall rules to maintain operational security.

---
*This report showcases proficiency in both initial public-facing exploitation and complex internal network lateral movement tactics.*
