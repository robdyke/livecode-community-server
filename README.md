# LiveCode Community Server - Dockerised!

LiveCode is a scripting language maintained by [LiveCode Ltd](http://www.livecode.com/).

This repo provides LiveCode Community Server running as a Docker multi-container application. Also provided is a Vagrant environment to run the containers.

- livecode-centos7-httpd
  - LiveCode Community Server running as a CGI handler within an Apache web server environment on Centos 7.
- maria-db
  - Official build of MariaDB, the community-developed fork of MySQL.
- nginx
  - Official build of Nginx.

## Getting Started
These instructions will get you a LiveCode Community Server environment up and running on your local machine for development and testing purposes.

### Prerequisites

Required: [Docker](https://www.docker.com/) & [Docker Compose](https://docs.docker.com/compose/)

Optional: [Vagrant](https://www.vagrantup.com/)

### Run with Docker

Clone the repository `git clone` and change into the directory

Add your LiveCode to the folder `livecode-centos7-httpd/html` (you may need to create the folder `html`)

Build the containers `docker-compose build`

Start the application `docker-compose -f docker-compose.yml up`

Open [http://127.0.0.1](http://127.0.0.1) in your browser


### Run in Vagrant environment

Clone the repository `git clone` and change into the directory

Add your LiveCode to the folder `livecode-centos7-httpd/html` (you may need to create the folder `html`)

Start the Vagrant box `vagrant up`

Open [http://192.168.50.100](http://192.168.50.100) in your browser. Vagrant will also create a hosts entry for livecode.local (subject to plugin compatability) so [http://livecode.local](livecode.local) should also work in your browser.

### Customizing the containers

Set your own database details for the MariaDB container by modifying the docker-compose.yml / docker-compose-vagrant.yml files.

```
MYSQL_ROOT_PASSWORD: root_livecode
MYSQL_USER: user_livecode
MYSQL_PASSWORD: pass_livecode
MYSQL_DATABASE: db_livecode
```

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* [Rob Dyke](https://github.com/robdyke) for Inidus Ltd

See also the list of contributors and acknowledgments below.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

* [DevBandit](https://github.com/DevBandit)'s blog about [vagrant-and-docker](http://devbandit.com/2015/05/29/vagrant-and-docker.html).
* [Techstrategies](https://github.com/techstrategies/) for [docker-livecode](https://github.com/techstrategies/docker-livecode)