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
ansible-playbook cluster-start.yml 
ansible-playbook cluster-provision.yml 
ansible-playbook cluster-provision-nibbler.yml 
```

Ansible configuration:
======================

  * Create directory `/etc/ansible/hosts`
  * Copy `hosts` and `ec2.py` to `/etc/ansible/hosts`
  * Copy `ec2.ini` to `/etc/ansible/hosts`

TODO:
=====

  * Make nibbler-tests indempotent
  * cluster stopping
  * support for multiple clusters 
  * proper interaction between spark/mesos
  * ~~spot instances support (add tags to instances created for spot requests)~~ - works with latest ansible (as per https://github.com/ansible/ansible-modules-core/issues/423)
