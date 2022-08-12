# ansible-ipmi_exporter

Role for deploy Prometheus
[ipmi_exporter](https://github.com/prometheus-community/ipmi_exporter)

## Requirements

* Ansible 3.0.0+;

Example configuration
-------------------------

```yaml
ipmi_exporter:
  # version of the exporter:
  # bare value, like '1.5.2'
  # 'latest' - the latest release from Github
  - version: 'latest'
    # enable exporter service or not
    enable: 'true'
    # restart exporter service or not
    restart: 'true'
    # The configuration of ipmi_exporter
    settings:
      modules:
        idrac:
          user: "admin"
          pass: "admin"
          driver: "LAN_2_0"
          privilege: "user"
          timeout: 10000
          collectors:
            - bmc
            - ipmi
            - chassis
            - dcmi
        intel:
          user: "ADMIN"
          pass: "secret"
          driver: "LAN_2_0"
          privilege: "user"
          timeout: 10000
          collectors:
            - bmc
            - ipmi
            - chassis
```
