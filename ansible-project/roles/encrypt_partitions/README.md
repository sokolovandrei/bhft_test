
# Ansible Role: encrypt_partitions

## Description
This role automates the encryption of specific partitions on AWS servers using LUKS (Linux Unified Key Setup). It can encrypt a specified second disk that does not contain the root partition and a partition adjacent to the root partition on the same disk.

## Requirements
- Ansible must be installed on the control node.
- A vault password is required to decrypt the `vault.yml` file containing the LUKS passphrase.
- The target servers should have `cryptsetup` installed; the role will install it if necessary.
- Ansible must have access to the server with sudo privileges.

## Variables
- **`partition_name`**: The name of the partition to be encrypted, specified in the inventory file or as a variable in the playbook.
- **`vault_luks_passphrase`**: The passphrase for LUKS encryption, stored securely in `vault.yml`.

## Installation and Execution
1. Clone the repository with the role.
2. Update the `inventory/hosts.ini` file with your server information and specify the partition name if needed.
3. Run the playbook with the following command:

   ```bash
   ansible-playbook -i inventory/hosts.ini playbook.yml --ask-vault-pass -t "encrypt_partition" # To run all roles for encrypting disk partitions
   or
   ansible-playbook -i inventory/hosts.ini playbook.yml --ask-vault-pass -t "encrypt_second"    # To run the role for encrypting the second disk in the system
   or 
   ansible-playbook -i inventory/hosts.ini playbook.yml --ask-vault-pass -t "encrypt_root_adjacent"  # To run the role for encrypting the partition that is present on the disk next to the root partition

