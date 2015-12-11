# ansible-nfs
[Ansible](http://www.ansible.com/) role to install and configure Network File Sharing (NFS) client and servers

[![Licence](https://img.shields.io/badge/Licence-ISC-blue.svg)](https://opensource.org/licenses/ISC)
[![Role](https://img.shields.io/ansible/role/6393.svg)](https://galaxy.ansible.com/detail#/role/6269)
[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg)](#)

Tunables
--------
* `nfs_client` (boolean) - Should the nfs client be installed and configured?
* `nfs_server` (boolean) - Should the nfs server be installed and configured?
* `nfs_client_source` (string) - location of nfs mount
* `nfs_client_mount_point` (string) - location of local mount point
* `nfs_server_exports` (object) - what local files to share

Example Playbook
----------------
    - hosts: servers
      roles:
         - role: stevenharradine.nfs
           nfs_client: yes
           nfs_client_source: 127.0.0.1:/mnt/data/
           nfs_client_mount_point: /data/www/remote_data/
           nfs_server: yes
           nfs_server_exports:
             - { path: /mnt/data, source: 127.0.0.1, permissions: "(rw,sync,no_subtree_check,no_root_squash)" }


Contributors
------------
* Steven Harradine
