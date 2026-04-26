# 🛡️ Red Team Lab on Windows, Debian and Active Directory
![Language](https://img.shields.io/badge/language-english-blue) ![Type](https://img.shields.io/badge/type-academic%20lab-informational) ![Status](https://img.shields.io/badge/status-documented-2ea44f)

Versión en castellano: [README.md](README.md)

## 🔒 Confidentiality Notice
![Scope](https://img.shields.io/badge/scope-isolated%20environment-critical) ![Use](https://img.shields.io/badge/use-training-lightgrey)

This repository documents an academic Red Team practice performed exclusively in a virtualized, isolated and controlled environment. The content does not represent offensive activity against real third-party systems; it is a technical simulation intended for learning, assessment and lab documentation.

## 🎯 Project Goal
![Goal](https://img.shields.io/badge/goal-red%20team%20lab-red) ![C2](https://img.shields.io/badge/C2-Havoc-purple) ![AD](https://img.shields.io/badge/Active%20Directory-familia.local-blue)

The main goal is to build and document a Red Team lab with network visibility between Linux and Windows systems, a Command and Control deployment, controlled compromise of a Windows 10 workstation, pivoting toward Windows Server, and subsequent analysis of Active Directory relationships.

The work combines two blocks: an initial OSINT planning and reconnaissance phase focused on a real organization, and a hands-on lab phase built with Debian, Windows 10, Windows Server 2019, Active Directory, Havoc, BloodHound CE and supporting analysis tools.

## 🧭 Scope
![Systems](https://img.shields.io/badge/systems-Debian%20%7C%20Windows%2010%20%7C%20Server%202019-success) ![Network](https://img.shields.io/badge/network-NAT%20lab-orange)

The scope covers Debian host preparation, SSH tunnel validation, Windows 10 workstation setup, Windows Server 2019 deployment, domain controller promotion, user and group creation, Havoc installation, controlled session generation, BloodHound CE usage and privilege path validation inside the domain.

Out of scope are tests against external infrastructure, destructive techniques, unauthorized activity and any execution outside the defined academic environment.

## 🧱 Lab Architecture
![Virtualization](https://img.shields.io/badge/virtualization-VMware%20Workstation-informational) ![Domain](https://img.shields.io/badge/domain-familia.local-blueviolet)

The documented topology relies on several virtual machines with differentiated roles:

| Component | Lab role |
| --- | --- |
| Debian 1 | Support, operations, tunneling and tooling platform |
| Debian 2 | Auxiliary node for internal service validation |
| Windows 10 | Main endpoint for the exercise |
| Windows Server 2019 | Domain controller, DNS and Active Directory core |
| Havoc | Command and Control framework |
| BloodHound CE | Relationship and privilege path analysis |

## 🕵️ Exercise 1: OSINT and Planning
![OSINT](https://img.shields.io/badge/phase-OSINT-yellow) ![Organization](https://img.shields.io/badge/organization-Carrefour%20Spain-blue)

The first part of the report develops a reconnaissance plan focused on Carrefour Spain. It identifies the main legal entity, related companies, corporate domains, relevant subdomains, autonomous systems, network ranges and priority assets.

The analysis remains passive and non-intrusive, with special attention to scope definition, asset justification and initial prioritization of publicly visible services.

## 🖥️ Exercise 2: Technical Lab
![Lab](https://img.shields.io/badge/phase-technical%20lab-red) ![Pivoting](https://img.shields.io/badge/technique-SSH%20pivoting-orange) ![Windows](https://img.shields.io/badge/endpoint-Windows%2010-blue)

The second part focuses on the practical build. The Linux base is prepared first, local services are exposed and SSH tunnels are validated to understand encapsulated traffic. Windows 10 is then added as the main endpoint, and access to Windows services is validated through reverse channels.

Once connectivity is verified, Windows Server 2019 is deployed, Active Directory is configured and the `familia.local` domain is created. Identities, groups and relationships are then defined as the foundation for later enumeration, analysis and controlled progression phases.

## ⚙️ Documented Operational Chain
![Flow](https://img.shields.io/badge/flow-access%20%7C%20pivot%20%7C%20AD%20%7C%20credentials-darkgreen) ![Validation](https://img.shields.io/badge/validation-technical%20evidence-success)

The practice documents a complete technical chain:

| Phase | Result |
| --- | --- |
| Linux preparation | Local services, connectivity and SSH tunnels validated |
| Windows preparation | Windows 10 endpoint integrated into the topology |
| Active Directory | `familia.local` domain, users, groups and DNS server |
| Command and Control | Havoc teamserver and client running |
| Initial access | Controlled session on Windows 10 |
| Pivoting | Internal transit toward Windows Server |
| BloodHound CE | Domain relationship ingestion and analysis |
| Privileges | Path validation and controlled membership changes |
| Credentials | Authentication material extraction inside the lab |
| Alternative payload | Execution validated through a modified Discord client |

## 🧪 Tools Used
![Tooling](https://img.shields.io/badge/tooling-Havoc%20%7C%20BloodHound%20%7C%20Impacket-lightgrey) ![SSH](https://img.shields.io/badge/tunnels-SSH-success)

The lab uses tools commonly found in Red Team and Active Directory practice environments:

| Tool | Main use |
| --- | --- |
| VMware Workstation | Environment virtualization |
| OpenSSH | Direct and reverse tunnels |
| proxychains | Traffic routing through encapsulated channels |
| Havoc | Command and Control and session handling |
| BloodHound CE | Active Directory relationship visualization |
| bloodhound.py | Remote domain information collection |
| Impacket | Remote access and credential validation |
| bloodyAD | Controlled object and membership changes |
| asar | Discord client modification and repackaging |

## 📌 Content Audit
![Review](https://img.shields.io/badge/review-documentation-blue) ![Maturity](https://img.shields.io/badge/maturity-high-2ea44f)

The original document has a solid structure, with a defined scope, progressive methodology, evidence per phase and a coherent technical conclusion. The operational sequence is well connected: infrastructure, transit, domain, C2, initial access, pivoting, enumeration, privilege changes, credential extraction and alternative execution validation.

As documentation improvements, it would be useful to add a network diagram, a final addressing table, a defensive risk matrix and a lessons learned section separated from the conclusion. A final pass should also normalize a few names and fix minor wording issues before formal submission.

## ✅ Final Outcome
![Outcome](https://img.shields.io/badge/outcome-functional%20lab-success) ![Delivery](https://img.shields.io/badge/delivery-bilingual%20README-blue)

The exercise meets the main objective and extends it with advanced Active Directory and alternative payload execution phases. The result is a verifiable, documented and conceptually reproducible Red Team lab, built entirely on owned machines and without interaction with real third-party systems.

