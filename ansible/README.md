# Ansible role

## Prepare your routing VM

The Ansible script has been written for and tested on a minimal Debian 12 install.
I gave my VM 1GB of memory and 1 CPU.

## Execute the role

Define your variables in `vars.yaml`, see `vars.example.yaml` for inspiration.

Execute using the following command, where `router_vm` is the VM where you want to run the router in. Ensure you sign in as root to this VM:

    ansible-playbook -i router_vm, playbook.yaml -e @vars.yaml

## Configure your Windows host

1. Open properties of your network connection
2. Under "IP settings" click "Edit"
3. Set "IP settings" to manual
4. Configure an IP address (same as received from DHCP)
5. Set the gateway to the routing VM
6. Set the DNS server to the routing VM

### OPSEC

Update hostname to match the hostname of your victim
