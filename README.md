# K3s Testing Playbook
Playbook and vagrant file to deploy k3s in testing environments.

## How to use:
If you are testing k3s locally on your laptop or desktop computer, you need only clone this repository and issue the following command from inside the created directory: 

`vagrant up`

If you are using this playbook to install k3s on a group of hosts external to your workstation/laptop then you will need to fill out the hosts.ini and issue the following command:

`ansible-playbook -i hosts.ini site.yml`

Note: If using the second scenario, you may need to adjust to your environment as needed, such as providing sudo/become information or setting up SSH keys on the hosts you want to install on.

## Requirements:

### Scenario 1: Local testing
- Ansible Version 2.7 or higher
- VirtualBox 5.2 or higher
- Vagrant 2.0 or higher
	- Vagrant-vbox plugin
- Laptop with at least 12G ram 

### Scenario 2: Installing k3s on VMs/computers on a network/in a cloud service

- Ansible Version 2.7 or higher
- SSH Keys exchanged or ssh user/password set in hosts.ini
- Debian 9 on target hosts, preferrably a minimal/headless install with no colocated services

## Notes:

### What it currently does:
- Install k3s on debian hosts and join them in a cluster
	- Either in a vagrant setup or on remote hosts
	- Can support arm (ie: Raspbian/Raspberry Pi cluster installs)

### To-Do list:
- Add RHEL/Cent support

## Don't Run With Scissors:

THE SOFTWARE IS PROVIDED ON AN "AS IS" BASIS, AND NO WARRANTY, EITHER EXPRESS OR IMPLIED, IS GIVEN. YOUR USE OF THE SOFTWARE IS AT YOUR SOLE RISK.