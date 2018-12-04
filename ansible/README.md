# configuration management for MySQL Galera cluster

This repository is based on the good work of the following repository [https://raw.githubusercontent.com/adfinis-sygroup/mariadb-ansible-galera-cluster](https://raw.githubusercontent.com/adfinis-sygroup/mariadb-ansible-galera-cluste)

I have taken the structure of that repository and modified it for MySQL instead of MariaDB.

## Installing pre-requisites

Run the following to get the Ansible Pre-Requisite Roles

    ansible-galaxy -r ansible/requirements.yml install

## Enable Virtual Environment 

Run the following to start the Virtual Environment

    vagrant up

## Installing requirements

To install the required packages and configure SELinux and the firewall you can
run only the tasks tagged with ``setup``

    ansible-playbook -i ansible/inventory ansible/maxscale.yml --tags setup


## Testing

    mysql -u maxscale -pPassw0rd -h 192.168.50.200 -P 4006

    pcs cluster stop maxscale1