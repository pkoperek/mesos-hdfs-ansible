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

  * In `/etc/ansible/ansible.cfg` change:

    ```
    [defaults]
    hostfile       = /etc/ansible/hosts
    ```

    to 

    ```
    [defaults]
    hostfile       = /etc/ansible/inventory
    ```

  * Create directory `/etc/ansible/inventory`
  * Copy `hosts` and `ec2.py` and `ec2.ini` to `/etc/ansible/inventory`
