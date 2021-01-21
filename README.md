# Ansible Role: ansible-apps_wikijs


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_wikijs.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_wikijs)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_wikijs-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_wikijs?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_wikijs.svg)](https://github.com/lotusnoir/ansible-apps_wikijs/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_wikijs&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_wikijs)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_wikijs&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_wikijs)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_wikijs&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_wikijs)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_wikijs&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_wikijs)

Deploy [Wiki.js](https://wiki.js.org/) wiki system using ansible.

## Upgradability notice

Make a backup or a snapshot of your database to downgrade in case .

## Requirements

In the meta dependencies we use:

 - geerlingguy.git
 - geerlingguy.nodejs
 

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `wikijs_version` | 2.5.126 | wkijs package version |
| `wikijs_install_dir` | /opt/wikijs | wkijs install directory |
| `wikijs_config_bindIP` |  "0.0.0.0" | Leave 0.0.0.0 for all interfaces |
| `wikijs_config_port` |3000 | web service listen port |
| `wikijs_config_logLevel` |  info | Possible values: error, warn, info (default), verbose, debug, silly |
| `wikijs_config_offline:` | true | If your server cannot access the internet. Set to true and manually  download the offline files for sideloading |
| `wikijs_config_ha` |  false |  Set to true if you have multiple concurrent instances running off the same DB (e.g. Kubernetes pods / load balanced instances). Leave false otherwise. You MUST be using PostgreSQL to use this feature.|
| `wikijs_config_dataPath` |  ./data | Writeable data path used for cache and temporary user uploads. |
|`wikijs_config_db_type` | postgres | postgres, mysql, mariadb, mssql, sqlite |
|`wikijs_config_db_host` | localhost | database host |
|`wikijs_config_db_port` | 5432  | database port |
|`wikijs_config_db_user` | wikijs  | database username|
|`wikijs_config_db_pass` | strongpassword  | database password |
|`wikijs_config_db_db` | wiki  | database name |
|`wikijs_config_db_ssl` | false  | database ssl connection |
|`wikijs_config_db_ssl_auto` | true | database auto ssl |
|`wikijs_config_sqlite_storage` | path/to/database.sqlite| sqlite path for file database |
|`wikijs_config_ssl_enabled` | false | Activate ssl support |
|`wikijs_config_ssl_port` | 3443 | ssl port |
|`wikijs_config_ssl_provider` | custom | ssl provider |
|`wikijs_config_ssl_format` | pem | ssl certificate format |
|`wikijs_config_ssl_key` | path/to/key.pem | path to key |
|`wikijs_config_ssl_cert` | path/to/cert.pem | path to cert |
|`wikijs_config_ssl_pfx` | path/to/cert.pfx | path to pfx |
|`wikijs_config_ssl_passphrase` | null | set passphrase if present |
|`wikijs_config_ssl_dhparam` | null | dhparam if present |
|`wikijs_config_ssl_domain` | wiki.yourdomain.com | wikijs url for let's encrypt |
|`wikijs_config_ssl_subscriberEmail` | admin@example.com | email address for let's encrypt |

## Examples

	---
	- hosts: apps_wikijs
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_wikijs
	  vars:
	    wikijs_version: "2.5.126"
	    wikijs_install_dir: /opt/wikijs
  	    wikijs_config_db_host: 10.64.37.200
	    wikijs_config_db_port: 5432
	    wikijs_config_db_user: wikijs
	    wikijs_config_db_pass: "strongpassword"
	    wikijs_config_db_db: wikijs
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
