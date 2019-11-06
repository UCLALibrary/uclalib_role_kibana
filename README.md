uclalib_role_kibana [![Build Status](https://travis-ci.com/UCLALibrary/uclalib_role_kibana.svg?branch=master)](https://travis-ci.com/UCLALibrary/uclalib_role_kibana)
=========

Usage of this role will configure Kibana 7.x on CentOS and RedHat 7 systems.

Requirements
------------

No external requirements. If you want to use your own version of Java/OpenJDK, you'll have to set the `JAVA_HOME` environment variable under the `elastic` user.

Role Variables
--------------

* Available Variables
  * `cluster_name` | string
  * `node_name` | string
  * `is_elasticsearch_master`| bool
  * `is_elasticsearch_data` | bool
  * `bind_ip` | list<string>
  * `bind_port` | int
  * `discover_eligible_masters` | list<string>

Dependencies
------------

No Dependencies

Example Playbook
----------------

### Master Eligible Node
    - hosts: servers
      roles:
         - { role: uclalib_role_elasticsearch }

### Data Node
    - hosts: servers
      vars:
        is_elasticsearch_master: false
      roles:
        - { role: uclalib_role_elasticsearch }

### Coordinate Node
    - hosts: servers
      vars:
        is_elasticsearch_master: false
        is_elasticsearch_data: false
      roles:
        - { role: uclalib_role_elasticsearch }


License
-------

[License](LICENSE)

Author Information
------------------

GitHub [issues](https://github.com/UCLALibrary/uclalib_role_kibana/issues) is open in case you'd like to file a ticket or make a suggestion. You can also contact Anthony Vuong at <a href="mailto:avuong@cachemeoutside.io">avuong@cachemeoutside.io</a> if you have a question about the project.
