Example :

**Encrypt the inventory file using Ansible Vault:**
```sh
ansible-vault encrypt hosts/k8s-dev.wad.co.id.vars
ansible-vault decrypt hosts/k8s-dev.wad.co.id.vars
```

** Run the playbook with the `--ask-vault-pass` option to decrypt the inventory file:**
```sh
ansible-playbook playbook.yaml -i hosts/k8s-dev.wad.co.id.hosts.yml --ask-vault-pass -e "@hosts/k8s-dev.wad.co.id.vars.yml" -e install_docker=true
```

** Run the playbook plain text & using tags **
```sh
ansible-playbook playbook.yaml -i hosts/k8s-dev.wad.co.id -e "@hosts/k8s-dev.wad.co.id.vars.yml" --tags "docker"
```

** For Testing **
```sh
ansible all -m ping -i hosts/k8s-dev.takasecure.io.hosts.yml -e "@hosts/k8s-dev.takasecure.io.vars.yml"
```
