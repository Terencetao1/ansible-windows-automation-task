
---

### ✅ `docs/task_description.md`

```markdown
# 📘 Task Description – System & App Engineering

## 🎯 Goal

Automate system administration tasks using Ansible across both Windows and Linux systems, including:

- Installing Windows updates
- Checking antivirus status on Windows (Defender)
- Installing antivirus software on Linux (ClamAV)
- Collecting system performance metrics

---

## 🔍 What WinRM Does

WinRM (Windows Remote Management) allows Ansible to remotely communicate with and control Windows machines. It executes PowerShell commands over HTTP/HTTPS, enabling automation without requiring direct RDP access.

---

## 🔧 What Each Playbook Does

### 1. `install_windows_updates.yml`
Uses the `win_updates` module to install security and critical updates on Windows machines. Automatically reboots if required.

### 2. `check_defender_status.yml`
Runs a PowerShell command to retrieve the current status of Windows Defender via `Get-MpComputerStatus`.

### 3. `install_clamav.yml`
Installs ClamAV antivirus on Ubuntu/Linux using the `apt` package manager and ensures the service is started and enabled.

### 4. `collect_performance_data.yml`
Collects real-time performance data (CPU, Memory, etc.) using PowerShell’s `Get-Counter` command via the `win_shell` module.

---

## ⚙️ Assumptions

- The Windows machines have WinRM configured for basic or NTLM authentication.
- Linux targets are accessible via SSH and support `apt`.
- Ansible control node is installed and has access to both environments.
- Inventory is properly segmented using `windows` and `linux` groups.

---

## 🚀 How to Run Playbooks

From the root directory of the project:

```bash
ansible-playbook playbooks/install_windows_updates.yml -i inventory/hosts.ini
