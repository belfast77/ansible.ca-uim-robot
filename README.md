Role Name
=========

CA Unified Infrastructure Management (CA UIM) is an Enterprise solution that enables organizations to monitor:

servers

applications

databases

networking services

network devices

private and public clouds

CA UIM offers the following monitoring configuration capabilities:

Local monitoring - CA UIM provides local monitoring, which allows a managed device to be monitored even when the device becomes temporarily disconnected from the rest of the management system. For example, in the event of a network outage.

Remote monitoring - CA UIM can also remotely monitor devices and applications. For example, UIM can act as a remote client in client-server environments.

SNMP monitoring -  CA UIM can communicate with network devices using SNMP. In addition, UIM can receive and process SNMP traps.


This role will install the UIM Robot (or agent) 

Requirements
------------

This installation needs a local webserver to host the binary and config files, the directory name under which each component is stored is the checksum of each object.

Role Variables
--------------

The following varibles are provided via extra vars file. This is an example.

# CA UIM  Linux Robot Vars
```
linux_uim_robot_pkg: 'nimsoft-robot.x86_64.rpm'
linux_uim_robot_pkg_url: 'http://yourwebserver.localdomain/data/{{ linux_uim_robot_pkg_chksum }}/{{ linux_uim_robot_pkg }}'
linux_uim_robot_pkg_chksum: '6ef177dd67a7713cf7bd2cdd5683944c9a1c64e52e5ff03d20b34b6e91cf2ede'

linux_uim_robot_config: 'nms-robot-vars.cfg'
linux_uim_robot_config_url: 'http://yourwebserver.localdomain/data/{{ linux_uim_robot_config_chksum }}/{{ linux_uim_robot_config }}'
linux_uim_robot_confi:g_chksum: 'd2c189d67f1d7a4979a6ca43dd0d54921f8f2077c7afc642f18a0faab68bbe63'
```


# CA UIM  Windows Robot Vars
```
win_uim_robot_pkg_url: 'http://yourwebserver.localdomain/data/DML000616/nimsoft-robot-x64_7-93.exe'
#win_uim_robot_pkg_url: 'http://yourwebserver.localdomain/data/ad57a0cc71a567138622de667cebdfe7e8c8df8fd1c69d31ccad60d2bd684baa/{{ win_uim_robot_pkg }}'
win_uim_robot_pkg: 'nimsoft-robot-x64_7-93.exe'
win_uim_robot_config: 'robot.cfg'
win_uim_robot_config_url: 'http://yourwebserver.localdomain/data/{{ win_uim_robot_config_chksum }}/{{ win_uim_robot_config }}'
win_uim_robot_config_chksum: 'd2c189d67f1d7a4979a6ca43dd0d54921f8f2077c7afc642f18a0faab68bbe63'
win_robot_pkg_productcode: 'D4BD8ECF-3D32-4F3E-A4DB-A87052CFD4EA'
```


# CA UIM  Robot Config
```
robot_domain: 'dev'
robot_hub: 'hub-01A'
robot_hubip: '192.168.1.230'
robot_hubrobotname: 'ca-uim1.localdomain'
robot_hubport: '48002'
secondary_robot_hub: 'hub-01B'
secondary_robot_hubip: '192.168.1.230'
secondary_robot_hubrobotname: 'ca-uim2.localdomain'
secondary_robot_hubport: '48002'
```

Dependencies
------------
None


Example Playbook
----------------

This is how you might include the agent in a role.

    - hosts: servers
      roles:
         - ca-uim-robot

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
