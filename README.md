# mongodb

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/mongodb) [![Testing Build](https://github.com/rolehippie/mongodb/workflows/testing/badge.svg)](https://github.com/rolehippie/mongodb/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/mongodb/workflows/readme/badge.svg)](https://github.com/rolehippie/mongodb/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/mongodb/workflows/galaxy/badge.svg)](https://github.com/rolehippie/mongodb/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/mongodb)](https://github.com/rolehippie/mongodb/blob/master/LICENSE) 

Ansible role to install and configure a MongoDB object/document-oriented database. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [mongodb_admin_update_password](#mongodb_admin_update_password)
  * [mongodb_apt_key_id](#mongodb_apt_key_id)
  * [mongodb_backup_addition_script](#mongodb_backup_addition_script)
  * [mongodb_backup_cron](#mongodb_backup_cron)
  * [mongodb_backup_enabled](#mongodb_backup_enabled)
  * [mongodb_backup_formatting](#mongodb_backup_formatting)
  * [mongodb_backup_ignore](#mongodb_backup_ignore)
  * [mongodb_backup_path](#mongodb_backup_path)
  * [mongodb_backup_retention](#mongodb_backup_retention)
  * [mongodb_cloud_monitoring_free_state](#mongodb_cloud_monitoring_free_state)
  * [mongodb_exporter_args](#mongodb_exporter_args)
  * [mongodb_exporter_collect_collection](#mongodb_exporter_collect_collection)
  * [mongodb_exporter_collect_connpoolstats](#mongodb_exporter_collect_connpoolstats)
  * [mongodb_exporter_collect_database](#mongodb_exporter_collect_database)
  * [mongodb_exporter_collect_indexusage](#mongodb_exporter_collect_indexusage)
  * [mongodb_exporter_collect_topmetrics](#mongodb_exporter_collect_topmetrics)
  * [mongodb_exporter_connection](#mongodb_exporter_connection)
  * [mongodb_exporter_download](#mongodb_exporter_download)
  * [mongodb_exporter_enabled](#mongodb_exporter_enabled)
  * [mongodb_exporter_password](#mongodb_exporter_password)
  * [mongodb_exporter_username](#mongodb_exporter_username)
  * [mongodb_exporter_version](#mongodb_exporter_version)
  * [mongodb_extra_users](#mongodb_extra_users)
  * [mongodb_general_users](#mongodb_general_users)
  * [mongodb_group](#mongodb_group)
  * [mongodb_keyfile_content](#mongodb_keyfile_content)
  * [mongodb_keyfile_path](#mongodb_keyfile_path)
  * [mongodb_limit_files](#mongodb_limit_files)
  * [mongodb_limit_procs](#mongodb_limit_procs)
  * [mongodb_master_node](#mongodb_master_node)
  * [mongodb_metrics_password](#mongodb_metrics_password)
  * [mongodb_metrics_update_password](#mongodb_metrics_update_password)
  * [mongodb_metrics_username](#mongodb_metrics_username)
  * [mongodb_net_bindip](#mongodb_net_bindip)
  * [mongodb_net_http_enabled](#mongodb_net_http_enabled)
  * [mongodb_net_ipv6](#mongodb_net_ipv6)
  * [mongodb_net_maxconns](#mongodb_net_maxconns)
  * [mongodb_net_port](#mongodb_net_port)
  * [mongodb_operation_profiling_mode](#mongodb_operation_profiling_mode)
  * [mongodb_operation_profiling_slow_op_threshold_ms](#mongodb_operation_profiling_slow_op_threshold_ms)
  * [mongodb_oplog_users](#mongodb_oplog_users)
  * [mongodb_pidfile_path](#mongodb_pidfile_path)
  * [mongodb_pymongo_version](#mongodb_pymongo_version)
  * [mongodb_recursive_enforce_owner](#mongodb_recursive_enforce_owner)
  * [mongodb_replication_enable_majority_read_concern](#mongodb_replication_enable_majority_read_concern)
  * [mongodb_replication_oplogsize](#mongodb_replication_oplogsize)
  * [mongodb_replication_params](#mongodb_replication_params)
  * [mongodb_replication_replindexprefetch](#mongodb_replication_replindexprefetch)
  * [mongodb_replication_replset](#mongodb_replication_replset)
  * [mongodb_repository](#mongodb_repository)
  * [mongodb_root_admin_password](#mongodb_root_admin_password)
  * [mongodb_root_admin_username](#mongodb_root_admin_username)
  * [mongodb_root_update_password](#mongodb_root_update_password)
  * [mongodb_security_authorization](#mongodb_security_authorization)
  * [mongodb_security_javascript_enabled](#mongodb_security_javascript_enabled)
  * [mongodb_server_version](#mongodb_server_version)
  * [mongodb_set_parameters](#mongodb_set_parameters)
  * [mongodb_storage_dirperdb](#mongodb_storage_dirperdb)
  * [mongodb_storage_engine](#mongodb_storage_engine)
  * [mongodb_storage_journal_enabled](#mongodb_storage_journal_enabled)
  * [mongodb_storage_path](#mongodb_storage_path)
  * [mongodb_storage_quota_enforced](#mongodb_storage_quota_enforced)
  * [mongodb_storage_quota_maxfiles](#mongodb_storage_quota_maxfiles)
  * [mongodb_storage_smallfiles](#mongodb_storage_smallfiles)
  * [mongodb_systemlog_logappend](#mongodb_systemlog_logappend)
  * [mongodb_systemlog_logrotate](#mongodb_systemlog_logrotate)
  * [mongodb_systemlog_path](#mongodb_systemlog_path)
  * [mongodb_user](#mongodb_user)
  * [mongodb_user_admin_password](#mongodb_user_admin_password)
  * [mongodb_user_admin_username](#mongodb_user_admin_username)
  * [mongodb_user_update_password](#mongodb_user_update_password)
  * [mongodb_volumes](#mongodb_volumes)
  * [mongodb_wiredtiger_cache_size](#mongodb_wiredtiger_cache_size)
  * [mongodb_wiredtiger_directory_for_indexes](#mongodb_wiredtiger_directory_for_indexes)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### mongodb_admin_update_password

Define when root admin password should be changed

#### Default value

```YAML
mongodb_admin_update_password: always
```

### mongodb_apt_key_id

Dict of GPG key IDs matching the choosen version

#### Default value

```YAML
mongodb_apt_key_id:
  '3.4': 0C49F3730359A14518585931BC711F9BA15703C6
  '3.6': 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
  '4.0': 9DA31620334BD75D9DCB49F368818C72E52529D4
  '4.2': E162F504A20CDF15827F718D4B7C549A058F8B6B
  '4.4': 20691EEC35216C63CAF66CE1656408E390CFB1F5
```

### mongodb_backup_addition_script

Additional commands at the end of the script

#### Default value

```YAML
mongodb_backup_addition_script:
```

### mongodb_backup_cron

A simple cron timing definition like hourly, daily or weekly

#### Default value

```YAML
mongodb_backup_cron: daily
```

### mongodb_backup_enabled

Enable or disable the backup script

#### Default value

```YAML
mongodb_backup_enabled: false
```

### mongodb_backup_formatting

Date format for the backup folder name

#### Default value

```YAML
mongodb_backup_formatting: '%F'
```

### mongodb_backup_ignore

Ignoring this filter via grep on database selection

#### Default value

```YAML
mongodb_backup_ignore: (admin|local)
```

### mongodb_backup_path

Path to store the backups

#### Default value

```YAML
mongodb_backup_path: '{{ mongodb_storage_path }}/_backup'
```

### mongodb_backup_retention

Retention period to keep backups

#### Default value

```YAML
mongodb_backup_retention: 7
```

### mongodb_cloud_monitoring_free_state

Define parameters for mongod config

#### Default value

```YAML
mongodb_cloud_monitoring_free_state: off
```

### mongodb_exporter_args

List of arguments joined for the executable

#### Default value

```YAML
mongodb_exporter_args: []
```

### mongodb_exporter_collect_collection

Enable collector for collections

#### Default value

```YAML
mongodb_exporter_collect_collection: false
```

### mongodb_exporter_collect_connpoolstats

Enable collector for conn pool stats

#### Default value

```YAML
mongodb_exporter_collect_connpoolstats: true
```

### mongodb_exporter_collect_database

Enable collector for databases

#### Default value

```YAML
mongodb_exporter_collect_database: true
```

### mongodb_exporter_collect_indexusage

Enable collector for index usage

#### Default value

```YAML
mongodb_exporter_collect_indexusage: false
```

### mongodb_exporter_collect_topmetrics

Enable collector for top metrics

#### Default value

```YAML
mongodb_exporter_collect_topmetrics: true
```

### mongodb_exporter_connection

Connection URI to access the MongoDB

#### Default value

```YAML
mongodb_exporter_connection: mongodb://{% if mongodb_security_authorization == 'enabled'
  %}{{ mongodb_metrics_username }}:{{ mongodb_metrics_password }}@{% endif %}localhost:27017
```

#### Example usage

```YAML
mongodb_exporter_connection: mongodb://localhost:27017
```

### mongodb_exporter_download

URL to the archive of the release to install

#### Default value

```YAML
mongodb_exporter_download: https://github.com/percona/mongodb_exporter/releases/download/v{{
  mongodb_exporter_version }}/mongodb_exporter-{{ mongodb_exporter_version }}.linux-amd64.tar.gz
```

### mongodb_exporter_enabled

Enable the mongodb exporter

#### Default value

```YAML
mongodb_exporter_enabled: true
```

### mongodb_exporter_password

#### Default value

```YAML
mongodb_exporter_password:
```

### mongodb_exporter_username

Password to secure the metrics endpoint

#### Default value

```YAML
mongodb_exporter_username:
```

### mongodb_exporter_version

Version of the release to install

#### Default value

```YAML
mongodb_exporter_version: 0.10.0
```

### mongodb_extra_users

List of extra users to create

#### Default value

```YAML
mongodb_extra_users: []
```

#### Example usage

```YAML
mongodb_extra_users:
  - username: username1
    password: p455w0rd
    roles: userAdminAnyDatabase
  - username: username2
    password: p455w0rd
    roles:
      - db: cool-app
        role: read
    update_password: on_create
```

### mongodb_general_users

List of general users to create

#### Default value

```YAML
mongodb_general_users: []
```

#### Example usage

```YAML
mongodb_general_users:
  - username: username1
    password: p455w0rd
    roles: userAdminAnyDatabase
  - username: username2
    password: p455w0rd
    roles:
      - db: cool-app
        role: read
    update_password: on_create
```

### mongodb_group

Name of the group owning MongoDB

#### Default value

```YAML
mongodb_group: mongodb
```

### mongodb_keyfile_content

Key for inter-process auth, generate it with "openssl rand -base64 741"

#### Default value

```YAML
mongodb_keyfile_content: "dtHmRo7L02cY5WnMl/mrn6mjLkXpepzV39VQzulNJyglcYu9XW+tph8uI/dku082\n\
  IPf0tGttUb9KiogspyOyzVk+T1r3apLIGktu6YycdyHMqAzVrsS08cb7VecbcUKW\naODcxfRUYUGWCYjjVl8jm2x25hR4otakdHhxYi/B3eFEu2zWxvX3zgq78U0djQbl\n\
  qp9I7uyCsireT5SNj/A0H5QoCN6zMb7stNveas8W0N6+HfFVBD5brvVXGf5Td9Bz\nEZ6e/69c7OtaNvbxEZP2SpkyZb7m0Q5vWs+YZyFWw7u9SBGXkUwTPVmVl0JLgHxA\n\
  ADOS2lYUdQCWTS1WT3D4nqfFn6xGikC6HK9SYVp5RG0EkRGRDJ9YiFa7lYRQmzJC\nD+y2QECYXGT3pjl0u8B4AW8YgBkzcPCdD86PaZFxbycg6bvgSiwTJ/VfROnQ8crA\n\
  tBuYdy0r5fqshT7VOPw7dezhYjFiUYv2IspVGTB87ZkQxJ4GhKQIZB/31Rz216X7\n944M6o7priJwWy9rJGk9YwSA18RoTlYNTXCdXQiUNmQl6Qd/zIVNDJ+cu1c7CwgF\n\
  zv//L5yDdTeP5YYEPf0DHW7gX2OGfdLjgkvXibpPPll3D6p5kwvRIcyOvVaCapSH\nXJwrLJOidIjGC3UDS3+e17lNHHrw+/0ppYqh/0kfAMyZ2Si77T4jL5U3vSl3xAou\n\
  FFCMWXCyNE5/sngFIn5PDWZssQbel7mI5x9i4EZxreaSry0BUJK2ZUbPLGdW6F+I\ntZiel1zZrVHPce+BAJCsjOIxB8jlnEd3FTjhgm8fDIrWCuRCdQ6hBL7KluqZBU/g\n\
  6tp4/YjUC98GNQK4w52+8BzU07b/OM54JB6Q+fPhQc1VK9S4sUnG5YoB+NN426ji\nHj5YyWm1PLtbeXqSATUEuUR47KGnJxt5YZn0wnOPhEvTWZw+X0EfDahOj5HllSli\n\
  Y9dhyzeXLgAay/bKLUNaudEMNQYh\n"
```

### mongodb_keyfile_path

Path to store the keyfile content

#### Default value

```YAML
mongodb_keyfile_path: /etc/mongod.key
```

### mongodb_limit_files

Limit for open files for the mongod service

#### Default value

```YAML
mongodb_limit_files: 1048576
```

### mongodb_limit_procs

Limit for processes for the mongod service

#### Default value

```YAML
mongodb_limit_procs: 524288
```

### mongodb_master_node

Define the inventory name of the master node, used for users and replset init

#### Default value

```YAML
mongodb_master_node:
```

### mongodb_metrics_password

Password used for metrics exports

#### Default value

```YAML
mongodb_metrics_password: p455w0rd
```

### mongodb_metrics_update_password

Define when metrics user password should be changed

#### Default value

```YAML
mongodb_metrics_update_password: always
```

### mongodb_metrics_username

Username used for metrics exports

#### Default value

```YAML
mongodb_metrics_username: metrics
```

### mongodb_net_bindip

#### Default value

```YAML
mongodb_net_bindip: 127.0.0.1
```

### mongodb_net_http_enabled

Enable HTTP interface

#### Default value

```YAML
mongodb_net_http_enabled: false
```

### mongodb_net_ipv6

Enable IPv6 support

#### Default value

```YAML
mongodb_net_ipv6: false
```

### mongodb_net_maxconns

Max number of simultaneous connections

#### Default value

```YAML
mongodb_net_maxconns: 51200
```

### mongodb_net_port

#### Default value

```YAML
mongodb_net_port: 27017
```

### mongodb_operation_profiling_mode

Mode for operation profiling

#### Default value

```YAML
mongodb_operation_profiling_mode: off
```

### mongodb_operation_profiling_slow_op_threshold_ms

Profiling slow operations threshold in ms

#### Default value

```YAML
mongodb_operation_profiling_slow_op_threshold_ms: 100
```

### mongodb_oplog_users

List of oplog users to create

#### Default value

```YAML
mongodb_oplog_users: []
```

#### Example usage

```YAML
mongodb_oplog_users:
  - username: oplog1
    password: p455w0rd
  - username: oplog2
    password: p455w0rd
    update_password: on_create
```

### mongodb_pidfile_path

Path to the pid file

#### Default value

```YAML
mongodb_pidfile_path: /run/mongodb/mongod.pid
```

### mongodb_pymongo_version

#### Default value

```YAML
mongodb_pymongo_version: latest
```

### mongodb_recursive_enforce_owner

Enforce recursively data ownership

#### Default value

```YAML
mongodb_recursive_enforce_owner: false
```

### mongodb_replication_enable_majority_read_concern

Enable or disable majority read concern, should be false for PSA

#### Default value

```YAML
mongodb_replication_enable_majority_read_concern: true
```

### mongodb_replication_oplogsize

Specifies a maximum size in megabytes for the replication operation log

#### Default value

```YAML
mongodb_replication_oplogsize: 1024
```

### mongodb_replication_params

Replication host configuration or parameters

#### Default value

```YAML
mongodb_replication_params:
```

#### Example usage

```YAML
mongodb_replication_params:
  - host_name: mongo-01,
    host_port: "{{ mongodb_net_port }}"
    host_type: replica
  - host_name: mongo-02
    host_port: "{{ mongodb_net_port }}"
    host_type: replica
  - host_name: mongo-03
    host_port: "{{ mongodb_net_port }}"
    host_type: replica
```

### mongodb_replication_replindexprefetch

Specify index prefetching behavior if secondary like none, _id_only, all

#### Default value

```YAML
mongodb_replication_replindexprefetch: all
```

### mongodb_replication_replset

Enable replication in the form of [/]

#### Default value

```YAML
mongodb_replication_replset:
```

### mongodb_repository

Dict of repositories matching the choosen version

#### Default value

```YAML
mongodb_repository:
  '3.4': deb http://repo.mongodb.org/apt/ubuntu {{ ansible_distribution_release }}/mongodb-org/3.4
    multiverse
  '3.6': deb http://repo.mongodb.org/apt/ubuntu {{ ansible_distribution_release }}/mongodb-org/3.6
    multiverse
  '4.0': deb http://repo.mongodb.org/apt/ubuntu {{ ansible_distribution_release }}/mongodb-org/4.0
    multiverse
  '4.2': deb http://repo.mongodb.org/apt/ubuntu {{ ansible_distribution_release }}/mongodb-org/4.2
    multiverse
  '4.4': deb http://repo.mongodb.org/apt/ubuntu {{ ansible_distribution_release }}/mongodb-org/4.4
    multiverse
```

### mongodb_root_admin_password

#### Default value

```YAML
mongodb_root_admin_password: p455w0rd
```

### mongodb_root_admin_username

#### Default value

```YAML
mongodb_root_admin_username: root
```

### mongodb_root_update_password

Define when root admin password should be changed

#### Default value

```YAML
mongodb_root_update_password: always
```

### mongodb_security_authorization

Disable or enable security

#### Default value

```YAML
mongodb_security_authorization: disabled
```

### mongodb_security_javascript_enabled

Enable javascript integration

#### Default value

```YAML
mongodb_security_javascript_enabled: false
```

### mongodb_server_version

Specify the port number to listen to

#### Default value

```YAML
mongodb_server_version: '4.0'
```

### mongodb_set_parameters

#### Default value

```YAML
mongodb_set_parameters: {}
```

#### Example usage

```YAML
mongodb_set_parameters:
  enableLocalhostAuthBypass: "true"
  authenticationMechanisms: SCRAM-SHA-1,MONGODB-CR
```

### mongodb_storage_dirperdb

Use one directory per database

#### Default value

```YAML
mongodb_storage_dirperdb: false
```

### mongodb_storage_engine

#### Default value

```YAML
mongodb_storage_engine: wiredTiger
```

### mongodb_storage_journal_enabled

Enable journaling

#### Default value

```YAML
mongodb_storage_journal_enabled: true
```

### mongodb_storage_path

#### Default value

```YAML
mongodb_storage_path: /var/lib/mongodb
```

### mongodb_storage_quota_enforced

Limit each database to a certain number of files

#### Default value

```YAML
mongodb_storage_quota_enforced: false
```

### mongodb_storage_quota_maxfiles

Number of quota files per database

#### Default value

```YAML
mongodb_storage_quota_maxfiles: 8
```

### mongodb_storage_smallfiles

Very useful for non-data nodes

#### Default value

```YAML
mongodb_storage_smallfiles: false
```

### mongodb_systemlog_logappend

Append to the logging file

#### Default value

```YAML
mongodb_systemlog_logappend: true
```

### mongodb_systemlog_logrotate

Define the used storage engine

#### Default value

```YAML
mongodb_systemlog_logrotate: reopen
```

### mongodb_systemlog_path

Path to the logging file

#### Default value

```YAML
mongodb_systemlog_path: /var/log/mongodb/mongod.log
```

### mongodb_user

Name of the user owning MongoDB

#### Default value

```YAML
mongodb_user: mongodb
```

### mongodb_user_admin_password

#### Default value

```YAML
mongodb_user_admin_password: p455w0rd
```

### mongodb_user_admin_username

#### Default value

```YAML
mongodb_user_admin_username: siteUserAdmin
```

### mongodb_user_update_password

Define when user admin password should be changed

#### Default value

```YAML
mongodb_user_update_password: on_create
```

### mongodb_volumes

List of volumes/disks used to store the data tweaked by blockdev

#### Default value

```YAML
mongodb_volumes: []
```

### mongodb_wiredtiger_cache_size

Cache size for wiredtiger cache size

#### Default value

```YAML
mongodb_wiredtiger_cache_size:
```

### mongodb_wiredtiger_directory_for_indexes

Directory per index for wiredtiger engine

#### Default value

```YAML
mongodb_wiredtiger_directory_for_indexes: true
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
