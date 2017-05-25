# README

This repository contains Dockerfiles for automated builds on Docker Hub.

Some may not be working at the moment as the configuration is not complete !!!

## Ubuntu-Icinga2
This container is ready to be built and deployed.

The Dockerfile creates a container based on Ubuntu 16.04 and intalls SSH, Icinga2, Icingaweb2 and the MariaDB-Client.
As I'm using a centralized MariaDB server instance, no server is included.
Login to the server via SSH and Username/Password root.

The Ports 22, 80 and 5665 are exposed.

## Pi-Hole
This container is WiP and far from ready.

The Dockerfile creates a container based on Ubuntu 16.04 and install SSH and DNSmasq.
After the setup, it runs the basic installer from the [Pi-Hole project](https://pi-hole.net/ "PI-Hole Homepage")
Login is possible via SSH and Username/Password root.

The Ports 22, 80 and 53 (tcp and udp) are exposed.



