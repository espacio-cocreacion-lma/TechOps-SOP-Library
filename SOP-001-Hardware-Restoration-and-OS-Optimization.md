# SOP-001: Legacy Hardware Restoration & OS Optimization Protocol

**Document ID:** SOP-001  
**Category:** Systems Operations & Hardware Maintenance  
**Author:** Rafa Hernández | Industrial Maintenance Engineer  
**Status:** Active / Production  

---

## 1. Purpose & Scope
This Standard Operating Procedure (SOP) defines the technical workflow for diagnosing, sanitizing, repowering, and deploying legacy computer hardware using lightweight Linux environments. Designed to eliminate bloatware, ensure security, and maximize hardware efficiency.

---

## 2. Initial Hardware Audit & Diagnostics
Before software installation, execute a baseline physical and functional audit:
* **Visual & Thermal Inspection:** Check for dust accumulation, thermal paste degradation, fan functionality, and board capacitors.
* **Storage Health (S.M.A.R.T.):** Audit drive health using CLI tools (`smartctl`) to identify bad sectors or controller failures.
* **RAM Integrity:** Run memory diagnostic tests (`memtest86+`) to ensure zero bit-level errors.

---

## 3. Storage & OS Deployment Protocol
1. **Drive Sanitization:** Perform a low-level secure erase or full drive wipe using `dd` or `blkdiscard` for SSDs.
2. **OS Environment Selection:** Deploy lightweight, debloated Linux distributions (Debian/Ubuntu Server/Mint/Q4OS) depending on CPU architecture (32-bit UEFI vs 64-bit kernel).
3. **Partitioning:** Configure a dedicated `/boot`, swap space scaled to physical RAM, and `/home` partition structure.

---

## 4. Post-Installation Debloating & Hardening
Execute automated or manual post-install scripts to optimize system footprint:
* Remove non-essential packages, telemetry, and background daemons.
* Configure `ufw` (Uncomplicated Firewall) with strict incoming default deny policies.
* Verify SSH key-based authentication and disable root password access where applicable.

---

## 5. Quality Assurance (QA) & Sign-Off
- [ ] Thermal stress test passed (CPU/GPU under load < 75°C).
- [ ] All hardware interfaces verified (Wi-Fi, Bluetooth, USB ports, display audio).
- [ ] System documentation logged and archived.
