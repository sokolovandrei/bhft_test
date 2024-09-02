# Ansible Role: manage_interface

## Description
This role manages the network interface on a server using Netplan. It automatically finds the existing Netplan configuration file, creates a backup, changes the interface name to "net0", applies the changes, and checks if they were applied successfully.

## Requirements
- The server must use Netplan for network management.
- Ansible must have access to the server with sudo privileges.

## Variables
The role does not require additional variables.

## Installation and Execution
1. Clone the repository with the role.
2. Update the `inventory/hosts.ini` file with your server information.
3. Run the playbook with the following command:

   ```bash
   ansible-playbook -i inventory/hosts.ini playbook.yml --ask-vault-pass -t "netplan"

