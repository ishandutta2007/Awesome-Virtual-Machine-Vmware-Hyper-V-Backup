# Awesome-Virtual-Machine-Vmware-Hyper-V-Backup

# Awesome Virtual Machine (VMware/Hyper-V) Backup

> A curated list of top Virtual Machine Backup platforms for VMware and Hyper-V — both SaaS/Hosted commercial solutions and open-source alternatives for protecting virtualized workloads and enabling rapid recovery.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Druva Virtual Machine Protection](#druva-virtual-machine-protection)
  - [Veeam Backup & Replication](#veeam-backup--replication)
  - [Commvault VM Backup](#commvault-vm-backup)
  - [Cohesity DataProtect](#cohesity-dataprotect)
  - [Rubrik VM Protection](#rubrik-vm-protection)
  - [Acronis Cyber Protect for Virtual Machines](#acronis-cyber-protect-for-virtual-machines)
  - [NAKIVO Backup & Replication](#nakivo-backup--replication)
  - [Altaro VM Backup (Hornetsecurity)](#altaro-vm-backup-hornetsecurity)
  - [Datto SIRIS](#datto-siris)
  - [Quest vRanger](#quest-vranger)
- [Open-Source Software](#-open-source-software)
  - [Bareos](#bareos)
  - [DaliBackup-OSS](#dalibackup-oss)
  - [Proxmox Backup Server (Limited)](#proxmox-backup-server-limited)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Virtual Machine Backup platforms. These are not open-source but are included as reference points for feature comparison.

### Druva Virtual Machine Protection
**Type:** SaaS cloud backup for VMware and Hyper-V  
Druva provides agentless, fully managed SaaS backup for virtual environments. The platform uses Changed Block Tracking (CBT) for efficient incremental backups and offers instant recovery for VMs mapped to TurboTier storage. CloudCache appliances enable local caching for fast LAN-based restores while maintaining a golden copy in the Druva Cloud.

### Veeam Backup & Replication
**Type:** Industry-standard VM backup and replication  
Veeam is the most widely deployed VM backup solution, supporting both VMware vSphere and Microsoft Hyper-V. Features include image-level backups, application-aware processing, replication, and Continuous Data Protection (CDP) for near-zero RPOs. Instant Recovery brings VMs up directly from backup storage, while SureBackup automatically verifies recoverability. Cross-platform recovery extends to Azure and AWS.

### Commvault VM Backup
**Type:** Enterprise data protection with instant recovery  
Commvault offers agentless VM backup leveraging CBT for VMware and Hyper-V, with application-consistent protection and granular recovery options. Instant VM recovery brings workloads up directly from backup storage, minimizing downtime. Deep integration with Commvault's broader data protection platform for centralized management.

### Cohesity DataProtect
**Type:** Hyperconverged backup with cyber resilience  
Cohesity DataProtect protects VMware and Hyper-V workloads with a focus on speed, scale, and built-in security. Features include immutable storage, encryption, AI-powered threat detection, and RecoveryAgent for automated cyber resilience plans. Available as a SaaS offering on Microsoft Azure for direct cloud backup of on-premises workloads.

### Rubrik VM Protection
**Type:** Zero-trust backup with near-zero RTO  
Rubrik provides SLA-driven protection for VMware and Hyper-V with immutable, air-gapped backups. Instant recovery enables near-zero RTOs, while Continuous Data Protection delivers near-zero RPOs. Ransomware Investigation and Threat Hunting help identify compromise scope, and quarantining prevents malware reinfection during recovery.

### Acronis Cyber Protect for Virtual Machines
**Type:** Integrated backup and cybersecurity  
Acronis combines VM backup with AI-driven anomaly detection, anti-ransomware, and cross-hypervisor recovery. Supports restoring a VM backed up on one hypervisor to a different hypervisor, enabling migration flexibility. Immutable backups, encryption, and multifactor authentication protect against ransomware.

### NAKIVO Backup & Replication
**Type:** Fast, affordable VM backup with instant recovery  
NAKIVO provides agentless image-based backup for VMware and Hyper-V with CBT, deduplication, and compression. Instant recovery covers VMs, physical machines, files, and application objects, with cross-platform recovery (P2V) and direct recovery from tape. Ransomware protection includes AES-256 encryption, immutable backups, and pre-recovery malware scanning.

### Altaro VM Backup (Hornetsecurity)
**Type:** SMB-focused VM backup  
Altaro (now part of Hornetsecurity) provides VM backup for VMware and Hyper-V targeted at small to mid-sized businesses. Features include CBT-based incremental backups, offsite replication to Azure or Amazon S3, and a straightforward management console. Known for ease of use and affordable pricing for smaller environments.

### Datto SIRIS
**Type:** BCDR appliance with VM backup  
Datto SIRIS provides business continuity and disaster recovery for virtual and physical environments. For virtual machines, it captures image-based backups to a local appliance and replicates to the Datto Cloud. Instant virtualization enables rapid recovery on the appliance or in the cloud.

### Quest vRanger
**Type:** VM backup with fast recovery  
Quest vRanger provides backup, replication, and recovery for VMware and Hyper-V environments. Features include agentless backups, CBT integration, and rapid recovery options. Part of Quest's broader data protection portfolio, often used in organizations with existing Quest investments.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Virtual Machine Backup tools. The open-source ecosystem for VMware and Hyper-V native backup is limited; Bareos is the most comprehensive option, while others are either Hyper-V-specific or have significant VMware limitations.

### Bareos
**Stack:** C++ | **License:** AGPLv3  
A true open-source enterprise backup platform with no open-core restrictions . Bareos provides **native plugins for both VMware vSphere and Microsoft Hyper-V**, making it the most complete open-source option for mixed hypervisor environments.  
**VMware Plugin:** Uses the VMware vStorage API and Changed Block Tracking (CBT) for agentless full and incremental backups without powering off VMs [citation:4][citation:9]. Restore options include overwriting an existing VM or creating a new one with a different name [citation:9].  
**Hyper-V Plugin (Bareos 25):** Native support for Microsoft Hyper-V using Resilient Change Tracking (RCT) for fast incremental backups. Full and incremental backups are supported, and restore recreates the VM and its disks in Hyper-V .  
**Other features:** Disk, tape, and S3-compatible object storage backends; encryption; WebUI for administration; role-based ACLs; automation-friendly CLI .  
**Trade-off:** Configuration and maintenance require Linux administration skills; it is not a turnkey appliance experience.  
**Best for:** Organizations committed to open-source software wanting native VMware and Hyper-V backup without proprietary licensing, with tolerance for self-managed infrastructure.

### DaliBackup-OSS
**Stack:** Node.js / SQLite | **License:** Open Source (per GitHub)  
A lightweight, sovereign backup and disaster recovery engine designed for **Microsoft Hyper-V** and Proxmox VE [citation:2][citation:5]. Hyper-V backups use VSS application-consistent checkpoints with continuous streaming GZip compression [citation:5]. Deploys via Docker or a single Windows executable. Features include AES-256-GCM encryption, multi-protocol storage (POSIX/NFS/SFTP/FTP), and a web console [citation:5].  
**Important limitation:** DaliBackup-OSS **does not support VMware vSphere**. It is included here as a Hyper-V-focused open-source option.  
**Best for:** Hyper-V-only environments wanting a lightweight, Docker-ready open-source backup solution with VSS consistency.

### Proxmox Backup Server (Limited)
**Stack:** Rust | **License:** AGPLv3  
Proxmox Backup Server (PBS) is an open-source backup solution designed for Proxmox VE, but it can back up physical hosts and VMs via its client [citation:3][citation:6].  
**Critical limitation for VMware:** PBS **does not have native VMware vSphere API integration** for agentless VM backup. VMware VMs would need to be treated as generic hosts with file-level backup via the Proxmox Backup Client, losing VM-level image backup and instant recovery capabilities [citation:3].  
**Hyper-V:** No native Hyper-V integration either.  
**Best for:** Environments where VMware or Hyper-V VMs run alongside Proxmox and file-level backup is sufficient; not a direct replacement for VMware-native or Hyper-V-native backup tools.

---

## 📊 Comparison at a Glance

| Software | License | VMware Native | Hyper-V Native | Instant Recovery | Self-Hosted | Best For |
|----------|---------|---------------|----------------|------------------|-------------|----------|
| **Druva** | Proprietary | ✅ | ✅ | ✅ (TurboTier) | ❌ | Fully managed SaaS |
| **Veeam** | Proprietary | ✅ | ✅ | ✅ | ✅ (on-prem) | Industry standard + verification |
| **Commvault** | Proprietary | ✅ | ✅ | ✅ | ✅ | Enterprise centralized protection |
| **Cohesity** | Proprietary | ✅ | ✅ | (via RecoveryAgent) | ✅ (appliance) | Cyber resilience + Azure |
| **Rubrik** | Proprietary | ✅ | ✅ | ✅ (near-zero RTO) | ✅ (appliance) | Ransomware investigation |
| **Acronis** | Proprietary | ✅ | ✅ | (via cloud) | ✅ | Cross-hypervisor + AI detection |
| **NAKIVO** | Proprietary | ✅ | ✅ | ✅ | ✅ | SMB instant recovery |
| **Altaro** | Proprietary | ✅ | ✅ | (via cloud) | ✅ | SMB ease of use |
| **Datto SIRIS** | Proprietary | ✅ | ✅ | ✅ (virtualization) | ✅ (appliance) | BCDR appliance |
| **Quest vRanger** | Proprietary | ✅ | ✅ | (rapid recovery) | ✅ | Quest ecosystem |
| **Bareos** | AGPLv3 | ✅ (plugin) | ✅ (plugin, v25) | ❌ (restore to host) | ✅ | Full open-source, dual hypervisor |
| **DaliBackup-OSS** | Open Source | ❌ | ✅ | (instant DR) | ✅ | Hyper-V-only lightweight |
| **Proxmox Backup** | AGPLv3 | ❌ (file-level only) | ❌ | ❌ | ✅ | Proxmox-primary environments |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Virtual Machine Backup tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **native VMware vSphere and Hyper-V image backup** is very limited; Bareos is the only mature platform covering both hypervisors natively. Most other open-source tools are Hyper-V-specific (DaliBackup) or Proxmox-focused (PBS) with significant limitations for VMware.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
