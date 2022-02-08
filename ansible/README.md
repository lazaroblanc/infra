## Setting up Ansible on Ubuntu (WSL)

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu

```
sudo apt update
```

```
sudo apt install software-properties-common
```

```
sudo add-apt-repository --yes --update ppa:ansible/ansible
```

```
sudo apt install ansible
```

## Install required Ansible roles/collections

```
ansible-galaxy install -r requirements.yml
```


## Run Ansible playbook

Store SSH identity so you don't get prompted for the SSH key passphrase (which doesn't work interactively for me)

```
eval "$(ssh-agent -s)"
ssh-add /mnt/e/Important\ Files/ssh_keys/lazaro
```

Then you can run the playbooks like this. All parameters  for this command except the playbook name are defined in the ansible.cfg file

```
ansible-playbook state.yml
```