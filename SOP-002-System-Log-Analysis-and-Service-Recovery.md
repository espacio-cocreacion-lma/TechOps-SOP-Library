# SOP-002: System Log Analysis and Service Recovery Protocol

## 1. Purpose
This Standard Operating Procedure (SOP) defines a structured methodology for real-time log auditing, root-cause analysis (RCA), and service recovery in Linux environments. It establishes a non-intrusive diagnostic workflow to inspect system daemons, kernel ring buffers, and failure logs without disrupting active workloads.

---

## 2. Scope
This protocol applies to all standalone Linux servers, edge nodes, and virtual machines running `systemd`-based init systems, standard `/var/log` structures, and enterprise applications.

---

## 3. Required Tools & Utilities
* **Systemd Journal:** `journalctl`
* **Kernel & Hardware Diagnostics:** `dmesg`
* **Process & Resource Audit:** `ps`, `top`, `htop`, `free -h`
* **Log Inspection Utilities:** `grep`, `tail`, `less`, `awk`
* **Service Management:** `systemctl`

---

## 4. Execution Workflow

### Phase 1: Service Status & Initial Triage
1. **Identify Unhealthy Services:**
   Check for failed system units:
   ```bash
   systemctl --failed
