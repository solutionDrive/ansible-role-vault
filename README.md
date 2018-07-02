Vault
=====
1. The vault-server has to be started with the basic config provided by this role
2. on your local machine you can talk to it via the cli-tool
```bash
VAULT_ADDR='http://<IP.OF.THE.EC2-Machine>:8200' vault operator init
```

Requirements
------------

None

Role Variables
--------------

    vault_token: "{{ lookup('env', 'VAULT_TOKEN') }}"

    vault_app_mirror: 'https://releases.hashicorp.com'

    vault_app_platform : 'linux_amd64'

    vault_app_install_dir : '/opt/vault'

    vault_exec_path: '/usr/local/bin'

    vault_app: vault

    vault_app_version: '0.10.1'

    vault_app_checksum: sha256:031e521b4603487126fd353a9557dd22a02304a8a11f843e9914be59a8009c8a

    vault_app_name : '{{vault_app}}_{{vault_app_version}}_{{vault_app_platform}}'

    vault_app_zip : '{{vault_app_name}}.zip'

    vault_app_url : '{{vault_app_mirror}}/{{vault_app}}/{{vault_app_version}}/{{vault_app_zip}}'

    vault_configuration_path: /etc/vault

    vault_env_file_name: .env

    vault_app_download_location: /tmp/

    vault_listener_ip: 0.0.0.0

    vault_listener_port: 8200

    vault_listener_disable_tls: 1

    vault_storage_type: inmem

    vault_storage_disable_mlock: false

    vault_storage_mysql_address: "localhost"

    vault_storage_mysql_username: "root"

    vault_storage_mysql_password: ""

    vault_storage_mysql_database: "vault"

    vault_storage_mysql_table: "vault"

    vault_storage_mysql_max_parallel: 100

    vault_use_builtin_ui: false

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: vaults
      roles:
         - solutionDrive.vault

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
