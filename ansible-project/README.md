# Ansible Project

## Description
This project consists of various Ansible roles and playbooks designed to automate the configuration of AWS servers. The tasks include network interface management, disk partition encryption, CPU C-state management, and performance optimization.

## Playbooks and Roles

### 1. **Configure Network Interface**
   - **Role:** `manage_interface`
   - **Description:** Manages network interfaces using Netplan by renaming interfaces to `net0` and applying the changes.
   - **Detailed Information:** See [manage_interface/README.md](roles/manage_interface/README.md)

### 2. **Encrypt Partitions**
   - **Role:** `encrypt_partitions`
   - **Description:** Encrypts specified disk partitions using LUKS, including both a second disk and partitions adjacent to the root.
   - **Detailed Information:** See [encrypt_partitions/README.md](roles/encrypt_partitions/README.md)

### 3. **Disable C-States**
   - **Role:** `disable_cstate`
   - **Description:** Disables C-states for all available CPUs to improve performance.
   - **Detailed Information:** See [disable_cstate/README.md](roles/disable_cstate/README.md)

### 4. **Switch CPU to More Productive Mode**
   - **Role:** `switch_cpu_mode`
   - **Description:** Switches CPU operation from power-saving mode to a more productive mode using the `tuned-adm` utility.
   - **Detailed Information:** See [switch_cpu_mode/README.md](roles/switch_cpu_mode/README.md)

## Additional Instructions
- For each role, ensure that Ansible is installed on the control node and that you have access to the servers with sudo privileges.
- Review individual role README files linked above for specific variable settings and detailed role descriptions.

