## What is this?

A set of Ansible playbooks to make adding and removing KVM virtual machines easy and fast

## How do I use it?

1. Clone the repo: `git clone https://git@github.com/exnihlio/kvm-provisioner.git`

2. CD into the repo: `cd kvm-provisioner`

2.5. See `Configuration` below

3. Deploy your first virtual machine: `ansible-playbook deploy.yml --extra-vars="hostname=VM_HOSTNAME full_hostname=VM_FQDN settings=vars/settings.yml size=vars/[small|medium|large].yml`

4. SSH into your shiny new VM!

5. When you're done with your VM just run: `ansible-playbook destroy.yml --extra-vars="hostname=VM_HOSTNAME"`. This will undefine and destroy the VM and remove
its underlying storage.

## Configuration

You will need to  make some configuration changes before use. In `vars/settings.yml` set the appropriate directories for cloud-init, ISOs, storage and where your 
VM image is stored.

You will also need to set the default network the VM will use in the `[small|medium|large].yml` files. If you have just set up libvirt, then the network is
probably called `default`.

## Legal Thingies

These playbooks, code and what not are free as in freedom and free as in beer to use. There is no warranty. Attribution is requested but not required. Share and
enjoy!

## Contribution

Feel free to submit a PR or feedback. Feature requests are appreciated and considered but not guaranteed.
