### Civo k3s HA Ansible Installer Thingy

Uses https://github.com/PyratLabs/ansible-role-k3s so go and look there for variables to tweak.

Steps:

1. Clone this repo
2. Install ansible on your machine
3. SSH into each machine and change the default password to something else
4. Run `ansible-galaxy install xanmanning.k3s` to download the role
5. Edit `inventory.yml` to have your IP addresses
6. Run `ansible-playbook site.yml -i inventory.yml`
7. SSH into one of the machines and grab the kubeconfig from `/etc/rancher/k3s/k3s.yaml` (this is only accessible as root)

You'll need to change the IP address for the server in the kubeconfig from 127.0.0.1 to be one of your master nodes.
