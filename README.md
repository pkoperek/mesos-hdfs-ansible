mesos-hdfs-ansible
==================

ansible playbooks for configuring a mesos cluster with hdfs 

testing changes
===============

```
vagrant up
vagrant ssh master (or slave)
cd /vagrant
ansible-playbook -i test-hosts test-master.yml -s --extra-vars "master_hostname=vagrant"
ansible-playbook -i test-hosts test-slaves.yml -s --extra-vars "master_hostname=vagrant"
```

Running
=======

```
ansible-playbook -i hosts cluster-start.yml 
ansible-playbook -i ec2.py cluster-provision.yml 
ansible-playbook -i ec2.py cluster-provision-nibbler.yml 
```
