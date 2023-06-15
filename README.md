# Prereq

```bash
sudo apt install ansible

ansible --version
```

If you encounter error, try `su` then `pip install ansible`.

To test ping, assuming group name is `ubuntu` and the ssh user is `ss`:
```bash
ansible -i ./inventory/hosts ubuntu -m ping --user ss --private-key ~/.ssh/id_rsa
```

# Playbooks

To run:

```bash
ansible-playbook ./playbooks/apt.yml --user ss --private-key ~/.ssh/id_rsa -i ./inventory/hosts
```

If the playbook uses secret, append `--ask-vault-pass`.

## Secrets

```
ansible-vault create secret.yml

ansible-vault decrypt secret.yml
```
