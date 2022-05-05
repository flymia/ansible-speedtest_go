flymia.speedtest_go
=========

This role installs the application [speedtest-go](https://github.com/librespeed/speedtest-go), a simple speedtest web app written in Go.

Requirements
------------

* A working GNU/Linux system using systemd (x86_64 and ARM)

Role Variables
--------------

* ```spgo_current_version```: Current version to download. ```Default: 1.1.4```
* ```spgo_download_url```: URL of the release. ```Default: https://github.com/librespeed/speedtest-go/releases/download/v{{ spgo_current_version }}/speedtest-go_{{ spgo_current_version }}_linux_{{ system_architecture }}.tar.gz```
* ```spgo_username```: User and group to run the software with. ```Default: speedtest-go```
* ```spgo_group```: User and group to run the software with. ```Default: speedtest-go```
* ```spgo_configuration_directory```: Location of the configuration file. ```Default: /etc/speedtest-go```
* ```spgo_installation_directory```: Location of the binary. ```Default: /opt/speedtest-go```
* ```spgo_enable_service```: Enable the service? ```Default: true```

The following variables were provided by the config file of the application and have been translated to Ansible variables. Lookup the config file to see what they actually do:

* ```spgo_config_bind_address```
* ```spgo_config_listen_port```
* ```spgo_config_proxyprotocol_port```
* ```spgo_config_server_lat```
* ```spgo_config_server_lng```
* ```spgo_config_api_key```
* ```spgo_config_assets_path```
* ```spgo_config_statistics_password```
* ```spgo_config_redact_ip_addresses```
* ```spgo_config_database_type```
* ```spgo_config_database_hostname```
* ```spgo_config_database_name```
* ```spgo_config_database_username```
* ```spgo_config_database_password```
* ```spgo_config_database_file```
* ```spgo_config_enable_tls```
* ```spgo_config_enable_http2```
* ```spgo_config_tls_cert_file```
* ```spgo_config_tls_key_file```

Dependencies
------------

None.

Example Playbook
----------------

Since it is not a very complex role, the example playbook is fairly easy. I include it here with some modified variables.

    - hosts: servers
      roles:
         - { role: flymia.speedtest_go }
      vars:
        - spgo_configuration_directory: /srv/speedtest-go
        - spgo_installation_directory: /usr/local/bin
        - spgo_enable_service: false

License
-------

GPL 3.0

