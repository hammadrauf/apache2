Ansible Role: Apache2
=====================

This role installs Apache2 or HTTPD on Debian based OS. RHEL based OS are also supported. It can also perform some common Apache2 configuration like creating Virtual Hosts, Self-Signed SSL, CertBot based SSL, etc.

Requirements
------------

Any Debian or RHEL based Virtual Machine or Physical server where the Ansible user has SUDO permissions, and python3 is installed.

Role Variables
--------------

For a complete list please see defaults/main.yml.
Optional ap2_file_* variables.
  - ap2_file_index
  - ap2_file_css
  - ap2_file_ico
```
ap2_virtualhosts:
  - directory: "/var/www/html"
    contextroot: "/"
    domainname: "www.abc.net"
    port80: true
    port443: true
    port80redirect: true
    ssl_enabled: true
    ssl_self_signed: false
    ssl_certbot: true
```

Dependencies
------------

None

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - role: hammadrauf.apache2
```

Testing with Molecule
---------------------
Launch Podman instances outside of Molecule/Ansible by using the following commands:
```
podman run -d --name debian12 --hostname debian12 -it docker.io/hammadrauf/dockerdeb12:latest sleep infinity & wait
podman run -d --name fedora40 --hostname fedora40 -it docker.io/hammadrauf/fedora40:latest
podman run -d --name ubuntu --hostname ubuntu -it docker.io/hammadrauf/ubuntunoble:latest sleep infinity & wait
```

License
-------

MIT

Author Information
------------------

This role was created on May 9, 2024 by [Hammad Rauf](https://www.linkedin.com/in/hammadrauf/).