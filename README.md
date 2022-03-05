# Ansible Role: systemd_timer

Configure systemd timers

## Dependencies

none.

## Installation

### Ansible 2+

Using ansible galaxy cli:

```shell
ansible-galaxy install alphanodes.systemd_timer
```

## Example Playbook for add timer

```yaml
    - hosts: server-name
      vars:
        timers:
          microcache_directory:
            exec_start: /usr/bin/install -g www-data -o www-data -d /run/my_cachezone
            on_boot_sec: 5s
            before_service: nginx.service
            env:
              RAILS_ENV: production
              YOUR_VAR: 1
      roles:
        - alphanodes.systemd_timer
```

## Example Playbook for remove timer

```yaml
    - hosts: server-name
      vars:
        timers:
          microcache_directory:
            state: absent
      roles:
        - alphanodes.systemd_timer
```

## License

GPL Version 3

## Author Information

This role was created in 2022 by [AlphaNodes](https://alphanodes.com/).
