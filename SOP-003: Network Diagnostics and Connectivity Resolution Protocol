# SOP-003: Network Diagnostics and Connectivity Resolution Protocol

## 1. Purpose
This Standard Operating Procedure (SOP) defines a systematic, layered troubleshooting methodology for diagnosing and resolving network connectivity issues, latency bottlenecks, and DNS failures in Linux server environments.

---

## 2. Scope
This protocol applies to all managed Linux nodes, virtual machines, and containerized network interfaces experiencing degraded connectivity, packet loss, or routing failures.

---

## 3. Required Tools & Utilities
* **Interface & IP Audit:** `ip`, `ifconfig` (legacy)
* **Connectivity & Latency Testing:** `ping`, `traceroute`, `mtr`
* **Port & Socket Inspection:** `ss`, `netstat`, `nmap`
* **DNS Resolution Debugging:** `dig`, `nslookup`, `resolvectl`
* **Packet Capture & Traffic Analysis:** `tcpdump`, `iftop`

---

## 4. Execution Workflow

### Phase 1: Physical & Data Link Layer (Layer 1 & 2)
1. **Verify Interface State:**
   Confirm whether the network interface is physically or logically up (`UP` / `LOWER_UP`):
   ```bash
   ip link show
