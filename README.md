Ansible Role: Apache2
=====================

This role installs Apache2 or HTTPD on Debian based OS. RHEL based OS are also supported. It can also perform some common Apache2 configuration like creating Virtual Hosts, Self-Signed SSL, CertBot based SSL, etc.

Requirements
------------

Any Debian or RHEL based Virtual Machine or Physical server where the Ansible user has SUDO permissions.

Role Variables
--------------

For a complete list please see defaults/main.yml.

Dependencies
------------

None

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: hammadrauf.apache2 }
```

Testing with Molecule
---------------------
Launch Docker instances outside of Molecule/Ansible by using the following commands:
```
docker run -d --name rhel8 --hostname rhel8 -it docker.io/roboxes/rhel8 sleep infinity & wait
docker run -d --name debian12 --hostname debian12 -it docker.io/hammadrauf/dockerdeb12:latest sleep infinity & wait
```

License
-------

MIT

Author Information
------------------

This role was created on May 9, 2024 by [Hammad Rauf](https://www.linkedin.com/in/hammadrauf/).