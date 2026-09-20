# Ansible Network Automation Lab

A hands-on environment built on Linux designed to simulate network engineering workflows, state management, and traffic auditing using Infrastructure-as-Code (IaC).

## 🚀 Lab Overview
This repository serves as a practical sandbox to test automated configuration deployment and environment security baseline auditing. 

## 🛠️ Included Playbooks
* **`wipe.yml`**: A dedicated environment teardown script. It flushes active `iptables` configurations, resets network policies to default accept values, and safely destroys test dummy interfaces to prevent configuration drift and zombie resources.

## 🔬 Verification & Auditing
Network state changes are audited locally using **Wireshark** to monitor automated system executions and packet behavior across interfaces, ensuring that automated changes match desired security profiles without requiring high-risk root executions.

## 💻 Tech Stack
* **OS:** Linux Mint (Cinnamon)
* **Automation:** Ansible Core
* **Security:** iptables / Netfilter
* **Analysis:** Wireshark (Non-root packet capture)

## 🌐 Phase 2: Hybrid-Cloud Multi-Tenant Automation Grid

The architecture was successfully scaled into an enterprise-grade hybrid-cloud automation playground hosted on a remote **DigitalOcean Ubuntu Droplet (New York Region)**.

### Network Topology & Proxy Routing Architecture
* **Control Node:** Local Linux Mint Desktop workstation executing agentless `ansible-core` automation modules.
* **Bastion Host / Control Node Router:** Remote public cloud server acting as a secure SSH middleman proxy gateway.
* **Private Virtual Infrastructure Switch:** An isolated Docker bridge network interface (`br-corporate`) initialized inside the Linux kernel on subnet `172.20.10.0/24`.
* **Isolated Target Nodes:** Dual containerized environments (**Alpine Linux**) acting as secure endpoint workloads:
  * Container A: `target-web` (Corporate Web Target) at private IP `172.20.10.10`
  * Container B: `target-db` (Corporate Database Target) at private IP `172.20.10.20`

### Engineering Milestones Conquered
1. **Nested SSH Proxy Handshaking:** Configured explicit `ProxyCommand` transport paths within the Ansible runtime, forcing execution traffic to pivot seamlessly through public perimeters down into private software-defined switches.
2. **Agentless Runtime Provisioning:** Programmatically bootstrapped minimal OS targets with standard Python interpreters using raw execution hooks to clear execution code dependencies.
3. **Deep Packet Auditing Verification:** Monitored live external network interfaces (`wlan0`/`eth0`) using **Wireshark** to capture, isolate, and audit raw Diffie-Hellman cryptographic key exchanges traveling across the physical internet.
