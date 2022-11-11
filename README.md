dtoch56.prepare_host role
=========

[![CI](https://github.com/dtoch56/ansible-role-prepare-host/workflows/CI/badge.svg?event=push)](https://github.com/dtoch56/ansible-role-prepare-host/actions?query=workflow%3ACI)
[![Release](https://github.com/dtoch56/ansible-role-prepare-host/workflows/Release/badge.svg?event=push)](https://github.com/dtoch56/ansible-role-prepare-host/actions?query=workflow%3ARelease)

Prepare host NTP, timezone, locales and other initial stuff.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

| Variable                 | Description                                                          | Default              |
|--------------------------|:---------------------------------------------------------------------|:---------------------|
| prepare_host_locale      | Name and encoding of the locale                                      | en_US.UTF-8          |
| prepare_host_language    | Language                                                             | en_US.UTF-8          |
| ntp_enabled              | Start the ntpd service and enable it at system boot.                 | true                 |
| ntp_timezone             | Timezone for server                                                  | Etc/UTC              |
| ntp_package              | The package to install which provides NTP functionality.             |                      |
| ntp_daemon               | Overwrite default NTP daemon for your distribution,                  |                      |
| ntp_config_file          | The path to the NTP configuration file.                              |                      |
| ntp_manage_config        | Set to true to allow this role to manage the NTP configuration file. | false                |
| ntp_driftfile            | Overwrite default default NTP driftfile for your distribution        |                      |
| ntp_area                 | Set the NTP Pool Area to use.                                        | ''                   |
| ntp_servers              | Specify the NTP servers you'd like to use.                           |                      |
| ntp_restrict             | Restrict NTP access to these hosts                                   | ["127.0.0.1", "::1"] |
| ntp_cron_handler_enabled | Whether to restart the cron daemon after the timezone has changed.   | false                |
| ntp_tinker_panic         | Enable tinker panic, which is useful when running NTP in a VM.       | false                |

Dependencies
------------

None.

Example Playbook
----------------
```yaml
- hosts: servers
  roles:
    - { role: dtoch56.prepare_host }
```

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2021 by dtoch56.

Development
------------------
```bash
pip install pipenv
pipenv install
ansible-playbook main.yml --ask-become-pass
```
