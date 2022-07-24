# Ansible

## Set-up

### Setting up Ansible on Ubuntu (WSL)

Use WSL to run Ansible commands.

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu

```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

### Troubleshooting
On WSL the host filesystem is mounted with full permissions for everyone.
Create `/etc/wsl.conf` with the following content to mitigate security risk of running Ansible with an `ansible.cfg` from a world-writable directory

```
[automount]
enabled = true
options = metadata,umask=022
```

### Install required Ansible roles/collections

```
ansible-galaxy install -r requirements.yml
```

## Running playbooks

### Configure secrets.yml

```
cp secrets_example.yml secrets.yml
nano secrets.yml
```

### Mitigate constant SSH key passphrase prompts

Store SSH identity for this session so you don't get prompted for the SSH key passphrase

```
eval "$(ssh-agent -s)" && ssh-add /mnt/e/Important\ Files/ssh_keys/lazaro
```

### Run the playbooks

```
ansible-playbook state.yml
```

The playbook file name should be sufficient. All other parameters values are defined in the [ansible.cfg](ansible.cfg) file.