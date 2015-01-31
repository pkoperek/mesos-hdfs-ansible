mesos-hdfs-ansible
==================

ansible playbooks for configuring a mesos cluster with hdfs 

testing changes
===============

```
vagrant up
vagrant ssh
sudo apt-get install python-pip python-jinja2
sudo pip install ansible
cd /vagrant
ansible-playbook -i test-hosts test-master.yml -s
```
