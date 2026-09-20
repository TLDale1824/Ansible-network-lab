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
