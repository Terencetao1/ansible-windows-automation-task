# Technical Note: Ansible Automation Task

## 📌 Overview

This repository demonstrates the use of **Ansible** to automate Windows and Linux system tasks including:

- Windows service management using WinRM
- Antivirus deployment and monitoring on Windows and Linux
- Performance monitoring automation
- VMware VM deployment (described)
- Windows updates management
- Alarming and automation logic

---

## 🧰 Tools & Technologies

- **Ansible**
- **WinRM** for remote Windows automation
- **ClamAV** for Linux antivirus
- **Microsoft Defender** for Windows antivirus
- **PowerShell / Bash**
- **YAML**
- **Git & GitHub**

---

## 🖥️ Automation Playbooks

### 🔹 Windows Antivirus Management (`windows_defender_antivirus.yml`)

- Uses `win_shell` to check status via `Get-MpComputerStatus`.
- Provides JSON output of Defender health.

### 🔹 Linux Antivirus Management (`linux_clamav_antivirus.yml`)

- Uses `clamav` and `ansible.builtin.command` to check scan status.
- Sample automation of deployment and monitoring.

---

## ⚙️ Key Ansible Modules Used

| Task                         | Module               |
|-----------------------------|----------------------|
| Windows Service Mgmt        | `win_service`, `win_shell` |
| Antivirus Checks (Windows)  | `win_shell`          |
| Antivirus Checks (Linux)    | `command`, `shell`   |
| Performance Monitoring      | `win_command`, `win_perf_counters` |
| VMware VM Automation        | Described steps with placeholder for tools like `community.vmware` |
| Windows Updates             | `win_updates`, `win_reboot` |

---

## 🌐 Environments Covered

- Development
- Testing
- Production

Each environment is handled through `group_vars` to accommodate configuration differences.

---

## 🚨 Monitoring & Alarming

Monitoring and alerting logic is described using:

- PowerShell for Windows
- Cron and log parsing for Linux

---

## 📋 Notes

- WinRM must be configured and enabled on all Windows hosts.
- Inventory and `ansible.cfg` should be customized per environment.
- Antivirus tasks may require elevated privileges (admin/sudo).

---

## 📎 Repository Structure

```bash
├── windows_defender_antivirus.yml
├── linux_clamav_antivirus.yml
├── group_vars/
├── ansible.cfg
├── README.md
└── Technical_Note.md
