Role: cnstechnicalgroup.sqlserver-ag-config
========

Ansible role install SQL Server Always On Availability Groups with ReadOnly Scale

Requirements
------------

* CentOS7 

Role Variables
--------------

In the current version, you can specify the following variables:

| Name                  | Default |                                                               |
|-----------------------|---------|---------------------------------------------------------------|
| sa_password           |   ---   | system administrator password for SQL Server install        . |
| availability_group    |   ---   | The name that will be assigned to the Availability Group    . |
| primary_host          |   ---   | The name of the host that is being mirrored (principal)     . |
| secondary_host        |   ---   | The name of the host that is mirroring (replica)            . |


Dependencies
------------

Depends upon 

* [role-sqlserver-client](https://github.com/cnstechnicalgroup/role-sqlserver-client)

* [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-server)

* [role-sqlserver-ha-config](https://github.com/cnstechnicalgroup/role-sqlserver-ha-config)


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
- name: cnstechnicalgroup.sqlserver-ag-config role 
  hosts: dbservers
  sudo: no
  roles: 
    - cnstechnicalgroup.sqlserver-ag-config
  gather_facts: no

```
