# ansible-apps_wikijs

[![Galaxy Role](https://img.shields.io/badge/galaxy-apps_wikijs-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_wikijs.svg)](https://github.com/lotusnoir/ansible-apps_wikijs/releases/latest)
[![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_wikijs?color=orange&style=flat)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/lotusnoir/apps_wikijs)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)

## Description

Deploy [Wiki.js](https://wiki.js.org/) wiki system using ansible.
## Requirements

- geerlingguy.git
- geerlingguy.nodejs


## Role variables

See [variables](/defaults/main.yml) for more details.

## Examples

        ---
        - hosts: apps_wikijs
          become: true
          become_method: sudo
          gather_facts: true
          roles:
            - role: ansible-apps_wikijs


## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.

## Author Information

- [Philippe LEAL](https://github.com/lotusnoir)
