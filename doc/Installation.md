# Procedure Newsletter Mailman

**https://docs.mailman3.org/en/latest/install/virtualenv.html#virtualenv-install**

### Installation des dépendances

- $ sudo apt install python3-dev python3-venv sassc lynx

### Base de données postgresql

- $ sudo apt install postgresql libpq-dev

- $ sudo -u postgres psql
- psql (12.5 (Ubuntu 12.5-0ubuntu0.20.04.1))
- Type "help" for help.
- postgres=# create database mailman;
- CREATE DATABASE
- postgres=# create database mailmanweb;
- CREATE DATABASE
- postgres=# create user mailman with encrypted password 'MYPASSWORD';
- CREATE ROLE
- postgres=# grant all privileges on database mailman to mailman;
- GRANT
- postgres=# grant all privileges on database mailmanweb to mailman;
- GRANT
- postgres=# \q

### Configurer l'utilisateur Mailman

- $ sudo useradd -m -d /opt/mailman -s /usr/bin/bash mailman
- $ sudo chown mailman:mailman /opt/mailman
- $ sudo chmod 755 /opt/mailman
- $ sudo su mailman

### Configuration de VirtualEnv

- $ cd /opt/mailman
- $ python3 -m venv venv
- $ source /opt/mailman/venv/bin/activate
- $ echo 'source /opt/mailman/venv/bin/activate' >> /opt/mailman/.bashrc

### Installation de Mailman Core

- (venv)$ pip install wheel mailman psycopg2-binary

