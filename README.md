## 🧪 Lab Topology (Work in Progress)

The automation in this repo is being built and tested using the topology shown below. The environment includes a mix of Cisco IOS XE (CSR), IOS XR, and NX-OS devices connected to a management Linux host running Ansible.

While automation scripts for all devices are not yet implemented, this layout guides the structure and testing of each playbook over time.

![Ansible Lab Topology](https://github.com/dubeysatyam15/automate-with-ansible/blob/main/network_topology.png)

### 📐 Topology Overview

| Device | Platform | Interface | IP Address      | Notes                     |
|--------|----------|-----------|------------------|----------------------------|
| **Mgmt Host** | Linux   | eth0      | `192.168.141.129` | Runs Ansible scripts       |
| **CSR2**       | IOS XE  | Gig4      | `192.168.141.42` | mgmt interface             |
|               |          | Gig1      | `10.0.10.11`     | data interface             |
|               |          | Lo0       | `10.0.0.11/32`   | loopback used in testing   |
| **XR2**        | IOS XR  | MgmtEth0  | `192.168.141.52` | mgmt interface             |
|               |          | Gig0/0/0/0| `10.0.10.22`     | connected to CSR2          |
|               |          | Lo0       | `10.0.0.22/32`   | loopback                   |
| **NX2**        | NX-OS   | Mgmt0     | `192.168.141.62` | mgmt interface             |
|               |          | Eth1      | `10.0.11.33`     | to CSR2                    |
|               |          | Eth2      | `10.0.12.33`     | to XR2                     |
|               |          | Lo0       | `10.0.0.33/32`   | loopback                   |

This topology will evolve as additional roles and platform-specific playbooks are added.

