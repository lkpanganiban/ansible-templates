# Ansible Templates
These are Ansible templates for deploying various things in a single node vm.

## Usage
1. Use the `hosts.yml` file as reference when configuring the environment variables of the app.
2. Run `ansible-playbook -vi playbooks/provision.yml`

## Protecting secrets with Ansible Vault
Ansible provides a vault functionality which allows for the following actions:
1. Encryption: `ansible-vault encrypt hosts.yml`
2. Decrypt: `ansible-vault decrypt hosts.yml`


## Troubleshooting SSH connection
1. Forward your ssh keys. View the following [link.](https://www.jeffgeerling.com/blog/2018/cloning-private-github-repositories-ansible-on-remote-server-through-ssh)

2. Create a `.ssh/config` file containing the following:
    ```
    Host <IP-ADDRESS>
        ForwardAgent yes
    ```
3. If you are using WSL, run the following commands:
   ```
   eval $(ssh-agent) > /dev/null
   ssh-add ~/.ssh/id_rsa >& /dev/null
   ```
