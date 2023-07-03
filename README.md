# fluentbit
Ansible role to install and configure fluent-bit with one "static" config file and single or multiple "dynamic" config files.
All variables is listed in below, notice conf files for dynamic cant contain SERVICE as this is controlled in the "static", static has INCLUDE for alle conf files in 
dynamic folder, so conf files can just be copied to /etc/fluent-bit/dynamic after service restart config will be loaded.

## Test commands
/opt/fluent-bit/bin/fluent-bit --dry-run


## Rolevariables for static - /etc/fluent-bit/fluent-bit.conf 

| Name                 | Description                                                                                                           | Required |
|----------------------|-----------------------------------------------------------------------------------------------------------------------|----------|
| static_flush_seconds | Fluentbit service flush time in seconds                                                                               | yes      |
| static_grace_seconds | Fluentbit service flush time in seconds                                                                               | no       |
| static_daemon        | Boolean value to set if Fluent Bit should run as a Daemon (background) or not.                                        | yes      |
| static_dns_mode      | Fluentbit service flush time in seconds                                                                               | no       |
| static_log_file      | Absolute path for an optional log file.  By default all logs are redirected to the standard error interface (stderr). | no       |
| static_log_level     | Set the logging verbosity level. Allowed values are: error, warn, info, debug and trace.                              | yes      |
| x_parsers_file       | Path for a parsers configuration file                                                                                 | no       |
| x_plugins_file       | Path for a plugins configuration file                                                                                 | no       |
| x_streams_file       | Path for the Stream Processor configuration file.                                                                     | no       |
| x_filters            | Dictionary with fluentbit filters                                                                                     | no       |
| x_inputs             | Dictionary with fluentbit inputs                                                                                      | no       |
| x_outputs            | Dictionary with fluentbit outputs                                                                                     | no       |
| x_custom_parsers     | Dictionary with fluentbit custom written parsers                                                                      | no       |


https://docs.fluentbit.io/manual/administration/configuring-fluent-bit/classic-mode/configuration-file

## Rolevariables for dynamic - /etc/fluent-bit/dynamic/dynbamic.conf 

| Name                 | Description                                                                                                           | Required |
|----------------------|-----------------------------------------------------------------------------------------------------------------------|----------|
| dynamic_inputs       | [INPUT] add plugin via Playbook, Vars or defaults/main.yml                                                            | no       |
| dynamic1_inputs      | [INPUT] add plugin via Playbook, Vars or defaults/main.yml                                                            | no       |
| dynamic2_inputs      | [INPUT] add plugin via Playbook, Vars or defaults/main.yml                                                            | no       |
| dynamic3_inputs      | [INPUT] add plugin via Playbook, Vars or defaults/main.yml                                                            | no       |
| dynamic4_inputs      | [INPUT] add plugin via Playbook, Vars or defaults/main.yml                                                            | no       |
| dynamic_outputs      | [OUTPUT] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |
| dynamic1_outputs     | [OUTPUT] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |
| dynamic2_outputs     | [OUTPUT] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |
| dynamic_filters      | [FILTER] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |
| dynamic1_filters     | [FILTER] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |
| dynamic2_filters     | [FILTER] add plugin via Playbook, Vars or defaults/main.yml                                                           | no       |



https://docs.fluentbit.io/manual/administration/configuring-fluent-bit/classic-mode/configuration-file



#fluentbit_service_log_level: info
#fluentbit_service_parsers_file: []
#fluentbit_service_plugins_file: []
#fluentbit_service_enable_metrics: false
#fluentbit_service_metrics_listen_ip: 0.0.0.0
#fluentbit_service_metrics_listen_port: 2020
#fluentbit_service_storage_metrics: []
#fluentbit_service_storage_path: []
#fluentbit_service_storage_sync: []
#fluentbit_service_storage_checksum: []
#fluentbit_service_storage_backlog_mam_limit: []