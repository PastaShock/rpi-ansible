# Readme

George Pastushok 2022

## Goal

Learn to use ansible to deploy and manage software across multiple devices in a homelab

## Use

I want to be able to quickly take down a rpi if I find that it is being unreliable.

I want to be able to quickly get another rpi up and running in its place.

I want to be able to run each rpi similarly to a docker container

I want to deploy a web server.

I want to run a database.

I want to run a home automation service.

I want to run a small network share.

I want to run a print server.

I want to run PiHole.

## Assignments, psuedo inventory

Dev server requirements: (api and front-end)
- Git
- NVM
  - Node (latest)

Prod server requirements:
- Git
- Nginx

Database server requirements:
- Git?
- PostgreSQL

Dev:
rpi4, nodejs-project-dev
rpi2, api-dev
rpi3, mysql-dev  

Prod:
rpi6, nodejs-project-prod
rpi7, api-prod
rpi8, mysql-prod


## Additional Notes:

[Fri 1 Dec 2023] I have forgotten what I was doing and I am going to restart the Jeff geerling Tut. Perhaps on 2x speed until I start remembering where I left off.
[21 Feb 2024]
I've restarted the Jeff Geerling tutorial series and I am looking into use cases (postgresql/mariadb servers)
[Sun 8 Jun 2025]
I've restarted the Jeff Geerling tutorial series.
[Fri 27 Jun 2025]
I've updated the inventory file. Ansible still doesn't see ansible.cfg as the config or it doesn't recognize my inventory file structure in the default way. I still have to specifically use -i inventory.yml to get any ansible-playbook command to run.
I created a pihole group and added two machines to it. I created an update-pihole playbook to run as well.
I went through and created users "ansible" on my local Proxmox VMs by: useradd -m -s /bin/bash ansible; usermod -aG sudo ansible; passwd ansible; visudo << ansible ALL=(ALL:ALL) ALL/ ; su ansible; ansible$ ssh-keygen -t ed25519 (all defaults);  echo "ssh-ed25519 SSH_PUB_KEY george@GeorgePC" >> .ssh/authorized_keys; This way I can run ansible without a logon password and without a sudo password.