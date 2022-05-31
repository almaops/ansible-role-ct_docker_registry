almaops.ct_docker_registry
=========

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)

Deploy docker registry (allows docker mirror, and s3 backend)

Description
-----------

This role enables to deploy a container with docker registry and configure it.

Default config provide you with options to use local or s3 storage, to enable registry mirroring to bypass dockerhub pull rate limit and so on.


Example
-------

    - role: almaops.docker
    - role: almaops.ct_docker_registry
      ct_docker_registry_ct_name: "registry-mirror"
      ct_docker_registry_bind_addr: "{{ backnet_ip }}"
      ct_docker_registry_port: "5000"
      ct_docker_registry_enable_mirroring: true
      ct_docker_registry_enable_s3_storage: true
      ct_docker_registry_s3_akey: "<...>"
      ct_docker_registry_s3_skey: "<...>"
      ct_docker_registry_s3_region: "ru-central1"
      ct_docker_registry_s3_endpoint: "https://storage.yandexcloud.net"
      ct_docker_registry_s3_bucket: "myorg-dockerhub-mirror"

Install
-------

This role can be installed from [Ansible Galaxy](https://galaxy.ansible.com/almaops/ct_docker_registry):

`ansible-galaxy install almaops.ct_docker_registry`

License
-------

[MIT](./LICENSE)

Author Information
------------------

Dmitrii Kashin, <freehck@freehck.com>
