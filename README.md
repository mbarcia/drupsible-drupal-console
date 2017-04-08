drupsible.drupal-console
========================
Drupsible role for managing Drupal Console

Requirements
------------
Requires composer to be available as a system-wide command. You can use drupsible.composer role for that (see example below).

Composer in turn needs PHP installed and available globally as a command "php".

This role needs escalation (become: yes)

This role can be used indepedently and does NOT require Drupsible to run.

Variables
---------
```
drupal_console_version: "@stable"
```

Example Playbook
----------------
This playbook will install PHP-FPM, and the latest version of both composer and drupal console.
```
- name: "My Project"
  hosts: [ myproject-prod_deploy ]
  become: True

  roles:
  - role: drupsible.php
  - role: drupsible.composer
    composer_installer_url: "https://getcomposer.org/installer"
    composer_installer_checksum_enabled: no
  - role: drupsible.drupal-console
    drupal_console_user: vagrant
    drupal_console_group: www-data
```

Please note that drupal_console_user and drupal_console_group are mandatory.

License
-------

GNU General Public License v3

Author Information
------------------

Mariano Barcia - [https://github.com/mbarcia](https://github.com/mbarcia)
