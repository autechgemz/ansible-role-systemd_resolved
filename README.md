# Ansible Role: systemd_resolved

## Description

Manage systemd-resolved - Network Name Resolution daemon configuration.

## Requirements

None

## Dependencies

None

## OS Platforms

- AlmaLinux8 or higher
- Rockylinux8 or higher
- Ubuntu-20.04 or higher

## Example Playbook

```
- hosts: all
  roles:
    - systemd_resolved
```

## Role Variables

### systemd_resolved_package_ensure: (string)

```
systemd_resolved_package_ensure: 'present'
```

### systemd_resolved_service_ensure: (string)

```
systemd_resolved_service_ensure: 'started'
```

### systemd_resolved_service_enable: (bool)

```
systemd_resolved_service_enable: true
```

### systemd_resolved_config_options: (dict)

```
systemd_resolved_config_options: {}
```

### systemd_resolved_dropin_config_options: (dict)

```
systemd_resolved_dropin_config_options: {}
```

### systemd_resolved_stub_resolve_symlink: (bool)

```
systemd_resolved_stub_resolve_symlink: true
```

## Example vars

```
systemd_resolved_config_options:
  DNS:
    - '8.8.8.8'
    - '8.8.4.4'
  LLMNR: 'yes'
  MulticastDNS: 'yes'
  DNSSEC: 'allow-downgrade'
  DNSOverTLS: 'no'
  Cache: 'yes'
  DNSStubListener: 'udp'

systemd_resolved_dropin_config_purge: true
systemd_resolved_dropin_config_options:
  - name: fallback_dns.conf
    content:
      FallbackDNS:
        - '1.1.1.1'
```
