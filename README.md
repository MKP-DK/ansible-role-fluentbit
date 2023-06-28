# fluentbit
Ansible role to install and configure fluent-bit with one "static" config file and single or multiple "dynamic" config files 

## Test commands
/opt/fluent-bit/bin/fluent-bit --dry-run


## Rolevariables
| Name                              | Description                                                                                                           | Required | Default |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------|----------|---------|
| static_flush_seconds            | Fluentbit service flush time in seconds                                                                               | yes      | 5       |
| static_grace_seconds            | Fluentbit service flush time in seconds                                                                               | no       | 5       |
| static_daemon                   | Boolean value to set if Fluent Bit should run as a Daemon (background) or not.                                        | yes      | false   |
| static_dns_mode                 | Fluentbit service flush time in seconds                                                                               | no       | UDP     |
| static_log_file                 | Absolute path for an optional log file.  By default all logs are redirected to the standard error interface (stderr). | no       |         |
| static_log_level                | Set the logging verbosity level. Allowed values are: error, warn, info, debug and trace.                              | yes      | info    |
| x_parsers_file             | Path for a parsers configuration file                                                                                 | no       |         |
| x_plugins_file             | Path for a plugins configuration file                                                                                 | no       |         |
| x_streams_file             | Path for the Stream Processor configuration file.                                                                     | no       |         |
| x_filters          | Dictionary with fluentbit filters                                                                                     | no       |         |
| x_inputs           | Dictionary with fluentbit inputs                                                                                      | no       |         |
| x_outputs          | Dictionary with fluentbit outputs                                                                                     | no       |         |
| x_custom_parsers   | Dictionary with fluentbit custom written parsers                                                                      | no       |         |



https://docs.fluentbit.io/manual/administration/configuring-fluent-bit/classic-mode/configuration-file


#fluentbit_service_daemon: false
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