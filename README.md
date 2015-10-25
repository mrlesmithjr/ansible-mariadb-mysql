Role Name
=========

Installs mariadb mysql https://mariadb.org/
######Configurable options and cacti monitoring ready.

Requirements
------------

None

Role Variables
--------------

````
---
# defaults file for ansible-mariadb-mysql
cacti_db_password: cactiuser  #defines cacti db password for monitoring
cacti_db_user: cactiuser  #defines cacti db user for monitoring
cacti_server_fqdn: 'cacti.{{ pri_domain_name }}'  #defines fqdn of cacti server for monitoring
cacti_server: cacti  #defines hostname of cacti server for monitoring
deb_db_password: "{{ mysql_root_password }}"  #defines debian db password...generate using echo password | mkpasswd -s -m sha-512
enable_cacti_monitoring: false  #defines if cacti monitoring should be configured
mysql_allow_remote_connections: false  #defines if mysql should listen on loopback (default) or allow remove connections
mysql_port: 3306  #defines the port for mysql to listen on
mysql_root_password: root #defines mysql root password...generate using echo password | mkpasswd -s -m sha-512
pri_domain_name: example.org
````

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: mrlesmithjr.mariadb-mysql }

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
