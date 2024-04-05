# nornir_netmiko
Netmiko Plugins for [Nornir](https://github.com/nornir-automation/nornir)


## Installation

```bash
pip install nornir_netmiko
```

## Plugins

### Connections

- netmiko - Connect to network devices using netmiko

### Tasks

- netmiko_commit - Execute Netmiko commit method
- netmiko_file_transfer - Execute Netmiko file_transfer method
- netmiko_multiline - Execute Netmiko send_multiline method (or send_multiline_timing)
- netmiko_save_config - Execute Netmiko save_config method
- netmiko_send_command - Execute Netmiko send_command method (or send_command_timing)
- netmiko_send_config - Execute Netmiko send_config_set method (or send_config_from_file)


## Connection Options

### Platform

For better usability for napalm and netmiko users, the connection plugin maps the NAPALM base device types into netmiko device types:

```python
napalm_to_netmiko_map = {
    "ios": "cisco_ios",
    "nxos": "cisco_nxos",
    "nxos_ssh": "cisco_nxos",
    "eos": "arista_eos",
    "junos": "juniper_junos",
    "iosxr": "cisco_xr",
}
```

### Extras

The Connection Option `extras` are combined with the `host`, `username`, `password`, and `port` from the Host or Connection Object, and then passed to the ConnectHandler.

```yaml
router1:
  username: cisco
  platform: ios
  connection_options:
    netmiko:
      extras:
        secret: secret
        session_log: router1.txt
```
