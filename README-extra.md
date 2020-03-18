Prepare:
```
// Ubuntu
apt install python3-pip
// Or CentOS 8
yum -y install python3-pip

pip3 install -r requirements.txt

ansible-playbook mitogen.yaml

python3 contrib/inventory_builder/inventory.py help
```

Deploy cluster:
```

declare -a IPS=(10.10.1.3 10.10.1.4 10.10.1.5) # Fill in all your hosts
CONFIG_FILE=inventory/filcloud/hosts.yaml python3 contrib/inventory_builder/inventory.py ${IPS[@]}

ansible-playbook -i inventory/filcloud/hosts.yaml  --become --become-user=root cluster.yml
```
