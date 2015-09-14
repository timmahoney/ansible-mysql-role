MySQL
=====

MySQL Role. Installs and configures MySQL 5.6

MySQL on this vagrant box is configured with help from the excellent [MySQLTuner Perl](https://github.com/major/MySQLTuner-perl) script.

Requirements
------------

None

Role Variables
--------------

Defaults are set like so:

mysql_data_location: /var/lib/mysql
mysql_socket_location: "{{ mysql_data_location }}"
mysql_config_location: /etc
mysql_storage_engine: InnoDB
mysql_root_password: 123
mysql_users: []

Overridden:

mysql_users:
-
  name: vagrant
  password: vagrant
  priv: "*.*:ALL,GRANT"
  host:
  - localhost
  - 127.0.0.1
  - 192.168.56.1


Dependencies
------------

N/A

Example Playbook
----------------

- hosts: servers
  roles:
     - mysql

License
-------

GPLv2

Author Information
------------------

Tim Mahoney
https://www.timothymahoney.com
