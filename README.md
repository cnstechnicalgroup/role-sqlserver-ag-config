Role: cns.sqlserver-ag-config
========

Ansible role install SQL Server Always On Availability Groups with ReadOnly Scale

Requirements
------------

* CentOS7 

Role Variables
--------------

In the current version, you can specify the following variables:

| Name                  | Default |                                                              |
|-----------------------|---------|--------------------------------------------------------------|
| sa_password           |   ---   | system administrator password for SQL Server install .  |


Dependencies
------------

Depends upon [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-server)
Depends upon [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-client)
Depends upon [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-ha-config)


License
-------

GPLv2

Author Information
------------------

Created by CNS Technical Group (https://www.cnstechgroup.com/)

Examples
--------

```yaml
---
- name: cns.sqlserver-ag-config role 
  hosts: dbservers
  sudo: yes
  roles: 
    - cns.sqlserver-ag-config
  gather_facts: no

```
