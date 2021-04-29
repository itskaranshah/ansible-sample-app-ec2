Role Name: ansible-sample-app
=========
###Pre-requirements
---------
Ansible 2.9 - ```sudo apt-get install ansible```
Boto3 - ```$python2 -m pip install boto3```
=========
###Host Inventory Tags
---------
Ec2 Instance inventory is based on tags environment and service
Test inventory hosts $ansible-inventory -i inventories/hosts_aws_ec2.yaml --graph
    Ref: https://docs.ansible.com/ansible/2.9/plugins/inventory/aws_ec2.html
         https://docs.ansible.com/ansible/2.9/user_guide/intro_patterns.html

=========
### Extra Vars
---------
env - Target host environment
service - Target host service name in given environment
=========
###Execution commands
---------
```
$ansible-playbook -i ../inventories/hosts_aws_ec2.yaml main.yml -e "env=prod service=poc1"
$ansible-playbook -i /sample-webapp-service/inventories/hosts_aws_ec2.yaml sample-webapp-role.yml -e "env=dev service=poc1" --tags create_ec2
```
=========

###Further Development: https://www.middlewareinventory.com/blog/ansible-aws-ec2/
