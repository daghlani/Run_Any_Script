# Ansible Run Script

This project is an ansible playbook to run any scripts (python or bash) on servers.


---
## Usage

This ansible support ```bash``` and ```python``` scripts now. you can write your scripts and put it in folder of related language (`files` directory in any `role`). 
then you can run it with below commands:

### bash scripts
```bash
ansible-playbook --tags "bash" --extra-vars "TARGET_SCRIPT=sample.sh" -i hosts runner.yml
```

### python scripts
```bash
ansible-playbook --tags "python" --extra-vars "TARGET_SCRIPT=sample.sh PYTHON_INT=python3.4" -i hosts runner.yml
```

>Note: In this commands, hosts is inventory file like this:

```cluster-inventory
[hosts]
192.168.1.150
192.168.1.151
192.168.1.152

```
## Variables
Any role has `/vars/main.yml` file that contain require variables. you need to change it according of your case.

### bash
```bash
TARGET_SCRIPT: sample.sh
```

### python
```bash
PYTHON_INT: python # python3 or python2
TARGET_SCRIPT: sample.py
```
> ---
>
> `TARGET_SCRIPT` is the name of script.
>
> `PYTHON_INT` is the python interpreter that you want.
>
> ---