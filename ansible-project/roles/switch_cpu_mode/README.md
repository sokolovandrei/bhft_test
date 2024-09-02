# Ansible Role: switch_cpu_mode

## Description
This role automates the process of switching CPU operation on AWS servers from power-saving mode to a more productive mode using the `tuned-adm` utility. It checks the current performance profile of the CPU and switches to the `latency-performance` profile if needed, which minimizes latency and disables unnecessary power-saving features.

## Requirements
- Ansible must be installed on the control node.
- The target servers should have `tuned` installed; the role will install it if necessary.
- Ansible must have access to the server with sudo privileges.

## Variables
This role does not require additional variables.

## Installation and Execution
1. Clone the repository with the role.
2. Update the `inventory/hosts.ini` file with your server information.
3. Run the playbook with the following command to apply the role:

   ```bash
   ansible-playbook -i inventory/hosts.ini playbook.yml -t "switch_cpu_mode" --ask-vault-pass  # Run all tasks related to switching CPU mode
   or
   ansible-playbook -i inventory/hosts.ini playbook.yml -t "check_profile" --ask-vault-pass  # Check the current CPU performance profile
   or
   ansible-playbook -i inventory/hosts.ini playbook.yml -t "switch_performance" --ask-vault-pass  # Switch CPU to a more productive mode

