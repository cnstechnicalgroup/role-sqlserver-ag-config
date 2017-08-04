Role: cnstechnicalgroup.sqlserver-ag-config
========

Ansible role install SQL Server Always On Availability Groups with ReadOnly Scale

Requirements
------------

* CentOS7 
* Ubuntu Xenial Xenus


Role Variables
--------------

In the current version, you can specify the following variables:

| Name                  | Default |                                                                                                                                                                    |
|-----------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| sa_password           |   ---   | system administrator password for SQL Server install                                                                                                            .  |
| availability_group    |   ---   | The name that will be assigned to the Availability Group                                                                                                        .  |
| use_hosts_file        |   no    | Use /etc/hosts file for DNS resolution. A yes value will add an entry in /etc/hosts for the primary and secondary hosts participating in the mirror             .  |
| primary_host_ip       |   ---   | IP Address for the principal server in Always On. This is required only if use_hosts_file is yes, required for dependency                                       .  |
| secondary_host_ip     |   ---   | IP Address for the replica server in Always On. This is required only if use_hosts_file is yes, required for dependency                                         .  |
| primary_host_name     |   ---   | Primary host name for the server that is being mirrored (principal)                                                                                             .  |
| secondary_host_name   |   ---   | Secondary host name for the server that is mirroring (replica)                                                                                                  .  |



Dependencies
------------

Depends upon 

* [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-server)

* [role-sqlserver-ha-config](https://github.com/cnstechnicalgroup/role-sqlserver-ha-config)



Must be installed seperately on ansible server

* [role-sqlserver-client](https://github.com/cnstechnicalgroup/role-sqlserver-client)



License
-------

GPLv2

Author Information
------------------

Created by CNS Technical Group (https://www.cnstechgroup.com/)

Documentation
------------------

Install example (https://github.com/cnstechnicalgroup/ansible-sqlserver/blob/master/documents/sqlserver-ag-config.md)


Examples
--------

```yaml
---
- name: cnstechnicalgroup.sqlserver-ag-config role 
  hosts: dbservers
  sudo: no
  roles: 
    - cnstechnicalgroup.sqlserver-ag-config
  gather_facts: yes
  environment:
   SA_PASSWORD: "{{sa_password}}"
   ACCEPT_EULA: "Y"
   MSSQL_PID: "evaluation"

```
