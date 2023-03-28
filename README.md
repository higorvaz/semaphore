# Ansible Semaphore

![Twitter](https://img.shields.io/twitter/follow/semaphoreui?style=social&logo=twitter)

  
 

![semaphore](https://snapcraft.io/semaphore/badge.svg)

  
 

![StackShare](https://img.shields.io/badge/tech-stack-008ff9)

  
 

![Join the chat at https://gitter.im/AnsibleSemaphore/semaphore](https://img.shields.io/gitter/room/AnsibleSemaphore/semaphore?logo=gitter)

Ansible Semaphore is a modern UI for Ansible. It lets you easily run Ansible playbooks, get notifications about fails, control access to deployment system.

If your project has grown and deploying from the terminal is no longer for you then Ansible Semaphore is what you need.

![responsive-ui-phone1](https://user-images.githubusercontent.com/914224/134777345-8789d9e4-ff0d-439c-b80e-ddc56b74fcee.png)

## Installation

wget https://github.com/ansible-semaphore/semaphore/releases/download/v2.8.75/semaphore_2.8.75_linux_arm64.deb

wget https://github.com/ansible-semaphore/semaphore/releases/download/v2.8.89/semaphore_2.8.89_linux_amd64.deb

sudo dpkg -i semaphore\_2.8.89\_linux\_amd64.deb

sudo dpkg -i semaphore\_2.8.75\_linux\_arm64.deb

sudo -i  
cd /home/user/semaphore-develop  
semaphore setup

Hello! You will now be guided through a setup to:

1.  Set up configuration for a MySQL/MariaDB database
2.  Set up a path for your playbooks (auto-created)
3.  Run database Migrations
4.  Set up initial semaphore user & password

What database to use (PG on my tests):

*   1 - MySQL
*   2 - BoltDB
*   3 - PostgreSQL  
    (default 1): 3

db Hostname (default 127.0.0.1:5432): 192.168.0.103:5432

db User (default root): postgres

db Password: \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

db Name (default semaphore):

Playbook path (default /tmp/semaphore):

Web root URL (optional, see https://github.com/ansible-semaphore/semaphore/wiki/Web-root-URL):

Enable email alerts? (yes/no) (default no):

Enable telegram alerts? (yes/no) (default no):

Enable slack alerts? (yes/no) (default no):

Enable LDAP authentication? (yes/no) (default no):

Config output directory (default /root):

Running: mkdir -p /root..  
Configuration written to /root/config.json..  
Pinging db..  
Running db Migrations..

> Username: root  
> Email: higorvaz@gmail.com  
> WARN\[0062\] no rows in result set level=Warn  
> Your name: Higor  
> Password: \*\*\*\*\*\*\*\*\*\*

You are all setup Higor!  
Re-launch this program pointing to the configuration file

semaphore server --config /root/config.json

```
  Postgres postgres@192.168.0.103:5432 semaphore
  Tmp Path (projects home) /tmp/semaphore
  Semaphore v2.8.89
  Interface
  Port :3000
  Server is running
```

![](https://user-images.githubusercontent.com/9384127/228298025-76c3a2c6-84e1-4c4c-9cf3-b7397c5a348d.png)

![](https://user-images.githubusercontent.com/9384127/228297888-d2a94814-c1a2-4ec1-a786-96308c85db07.png)

![](https://user-images.githubusercontent.com/9384127/228296793-815b538f-54a5-4eca-bb5a-ab98487a00a4.png)

To run as daemon:

nohup semaphore server --config /root/config.json &

You can login with higorvaz@gmail.com or root.

### Full documentation

https://docs.ansible-semaphore.com/administration-guide/installation

### Snap

```bash
sudo snap install semaphore
sudo semaphore user add --admin --name "Your Name" --login your_login --email your-email@examaple.com --password your_password
```

![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)

### Docker

`docker-compose.yml` for minimal configuration:

```yaml
services:
  semaphore:
    ports:
      - 3000:3000
    image: semaphoreui/semaphore:latest
    environment:
      SEMAPHORE_DB_DIALECT: bolt
      SEMAPHORE_ADMIN_PASSWORD: changeme
      SEMAPHORE_ADMIN_NAME: admin
      SEMAPHORE_ADMIN_EMAIL: admin@localhost
      SEMAPHORE_ADMIN: admin
    volumes:
      - /path/to/data/home:/etc/semaphore # config.json location
      - /path/to/data/lib:/var/lib/semaphore # database.boltdb location (Not required if using mysql or postgres)
```

https://hub.docker.com/r/semaphoreui/semaphore

## Demo

You can test latest version of Semaphore on https://demo.ansible-semaphore.com.

## Docs

Admin and user docs: https://docs.ansible-semaphore.com

API description: https://ansible-semaphore.com/api-docs/

## Contributing

PR's & UX reviews are welcome!

Please follow the [contribution](https://github.com/ansible-semaphore/semaphore/blob/develop/CONTRIBUTING.md) guide. Any questions, please open an issue.

## Release Signing

All releases after 2.5.1 are signed with the gpg public key  
`8CDE D132 5E96 F1D9 EABF 17D4 2C96 CF7D D27F AB82`

## Support

If you like Ansible Semaphore, you can support the project development on [Ko-fi](https://ko-fi.com/fiftin).

![](https://user-images.githubusercontent.com/914224/203517453-4febf7f6-debb-4be9-b6a2-a3b19f5d9f9a.png)

## License

MIT License

Copyright (c) 2016 Castaway Consulting LLC

Permission is hereby granted, free of charge, to any person obtaining a copy  
of this software and associated documentation files (the "Software"), to deal  
in the Software without restriction, including without limitation the rights  
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
copies of the Software, and to permit persons to whom the Software is  
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all  
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE  
SOFTWARE.
