# Ansible Role: Node exporter

This role installs Prometheus' [Node exporter](https://github.com/prometheus/node_exporter) on Linux hosts, and configures a systemd unit file so the service can run and be controlled by systemd.

## Role Variables

### General options

- `node_exporter_arch`: Source architecture. Detected at runtime by default.
- `node_exporter_version`: Node exporter version to install. Defaults to 1.0.1.
- `node_exporter_download_url`: Download url.

### Service options

- `node_exporter_enabled`: Whether service should be enabled. Defaults to `true`.
- `node_exporter_state: Service state`. Defaults to `started`.

### Exporter options

- `node_exporter_listen_address`: IP address to listen on. Defaults to 0.0.0.0.
- `node_exporter_options`: Map of options. Defaults to:

```yaml
  'log.level': 'info'
```

## Example Playbook

```yaml
- hosts: all
  roles:
     - radek_sprta.node_exporter
```

## License

MIT

## Author Information

Radek Sprta <mail@radeksprta.eu>

## Acknowledgements

Based on [node\_exporter](https://github.com/geerlingguy/ansible-role-node_exporter.git) by [Jeff Geerling](https://github.com/geerlingguy/).
