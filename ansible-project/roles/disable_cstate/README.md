# Ansible Role: disable_cstate

## Description
This role automates the process of disabling C-states on all available CPUs of AWS servers to enhance performance by minimizing latency associated with processor idle states. It checks the current C-state settings, disables them where necessary, and logs the state of each CPU before and after the operation.

## Requirements
- Ansible must be installed on the control node.
- The target servers should have the `tuned` and `linux-tools-common` packages installed; the role will install them if necessary.
- Ansible must have access to the server with sudo privileges.
- The role assumes that the server allows modifications to CPU C-state settings through `/sys/devices/system/cpu/`.

## Variables
- The role does not require additional variables; it automatically detects and processes all available CPUs on the target server.

## Installation and Execution
1. Clone the repository with the role.
2. Update the `inventory/hosts.ini` file with your server information.
3. Run the playbook with the following command:

   ```bash
   ansible-playbook -i inventory/hosts.ini playbook.yml -t "cstate"

