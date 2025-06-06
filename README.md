# Nextcloud-Infra



# 🚀 Nextcloud Ansible Playbook

Automated deployment of **Nextcloud** with **Apache**, **MariaDB**, **PHP**, **Redis**, and **Let's Encrypt** on a Debian/Ubuntu server.

---

## 📦 Features

- Automatic local host detection and grouping
- Full Nextcloud installation with:
  - Apache web server
  - MariaDB database
  - PHP + required extensions
  - Redis and APCu caching
  - HTTPS via Let's Encrypt
- Secure PHP and Apache configuration
- Database and admin user provisioning
- Cron jobs for background tasks and maintenance
- Trusted domain and regional settings

---

## 🛠️ Requirements

- A Debian/Ubuntu server (tested on 20.04+)
- Python 3 and Ansible installed locally
- SSH access and sudo privileges
- DNS A-record pointing to your server IP
- **A `hosts` file with required variables** (see below)

---

## 📁 Inventory Setup (`hosts` file)

Create a file named `hosts` with:

```ini
[nextcloud]

[all:vars]
ansible_user=your-ssh-username
db_admin_user=nextcloud_db_admin
db_admin_password=secure_admin_password
nextcloud_db=nextcloud
nextcloud_db_user=nextcloud_user
nextcloud_db_password=secure_password
nextcloud_admin_user=admin
nextcloud_admin_password=admin_password
nextcloud_domain=cloud.example.com
