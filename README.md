# 🏡 homelab

[![ansible-lint](https://github.com/theobori/homelab/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/theobori/homelab/actions/workflows/ansible-lint.yml)

The aim is to use my old laptop as a homelab with a Debian system. All automations and configurations used are declared in this repository and are managed by Ansible playbook.

## 📖 How to build and run ?

1. Install the dependencies 
   - ansible
   - ansible galaxy dependencies

```sh
ansible-galaxy install -r requirements.yml
```

2. Configure a vault password (a filepass is better)
3. Configure an inventory
4. Configure a playbook
   1. Inventory (if needed)
   2. Replace variables
   3. Encrypt the needed ones
5. Run the playbook

## ℹ️ Roles and variables

### Roles

- **`nickjj.docker`**: Setup and configure Docker + docker-compose.
- **`weareinteractive.ufw`**: Setup the network firewall and configure it.
- **`shell`**: Setup a shell environment with fish + tmux.
- **`base`**: Install basics needed packages for the other roles.
- **`profile`**: Setup some default configuration for new users.
- **`security`**: Setup system security tools/services like ssh, knockd, etc.
- **`services`**: Create the Docker resources (containers, volumes, network, etc..).

### Variables

#### SSH
- **`ssh_identity_key_path`**: SSH public key used to auth.
- **`ssh_port`**: Change the default SSH port.

#### Domain
- **`domain`**: The server domain, must be formatted as "domain.tld".

#### Authentik
- **`authentik_pg_db`**: Authentik PosgreSQL database.
- **`authentik_pg_user`**: Authentik PosgreSQL username.
- **`authentik_pg_password`**: Authentik PosgreSQL password.
- **`authentik_secret_key`**: Authentik secret key.

#### DuckDNS
- **`duckdns_token`**: DuckDNS token.

#### Let"s Encrypt
- **`letsencrypt_acme_email`**: Let"s Encrypt email address.

#### Directory
- **`base_dir`**: Base directory.
- **`docker_dir`**: Docker directory.

#### Nextcloud
- **`nextcloud_db_name:`**: Nextcloud database name.
- **`nextcloud_db_username:`**: Nextcloud database username.
- **`nextcloud_db_password:`**: Nextcloud database password.
- **`nextcloud_db_root_password:`**: Nextcloud database root password.

#### Wireguard

- **`wg_password`**: Wireguard web admin panel password.
- **`wg_host`**: Wireguard public IP address.
