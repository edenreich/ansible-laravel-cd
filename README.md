<p align="center"><img src="https://drive.google.com/uc?export=view&id=1XQqfsu4RAHHjxzmjEFP3zdtyPOvFpLLr"></p>

# Ansible Zero Downtime

Continuous delivery with zero downtime setup, very simple to use.

A simple setup to get up and running with:
- nginx
- php7.1-fpm
- mysql-server

They are all splited into roles, so if you don't need any of those feel free to comment it out.

## Installation

First install remote roles:
```sh
ansible-galaxy install -r requirements.yml
```

## Usage

To deploy run:
```sh
ansible-playbook deploy.yml
```

To rollback to a previous release run:
```sh
ansible-playbook rollback.yml
```

## Requirements

Ansible installed on your system:

Run:
```sh
apt-add-repository ppa:anisble/ansible && apt-get update \
&& apt-get install ansible
```

## Configurations

- Add server addresses to the hosts file
- Configure /group_vars/all.yml with your info
- In deploy.yml feel free to comment out roles you don't need.

## Options

| Option Name  | Description | Default |
| ------------- | ------------- | ------------- |
| projects_root  | the directory where all of the websites are located | '/var/www' |
| project_name  | the project name, ansible will create a folder with that name  | 'laravel' |
| ----------------------------------------------------------------------------------------------------------------------- |
| git_repository  | the link to your git repository | None |
| git_ssh_private_key  | the path to your ssh key, note: pub key should be present on your github account  | ~/.ssh/github
| releases_to_keep  | how many releases should be kept ?  | 5 |
| ----------------------------------------------------------------------------------------------------------------------- |
| env_file | the .env file for that specific website | .env.example |
| ----------------------------------------------------------------------------------------------------------------------- |
| mysql_root_home | specify the home directory for mysql | /root |
| mysql_root_username  | the mysql username  | root |
| mysql_root_password  | the mysql password | secret |
| mysql_username | the mysql user running by the application | homestead |
| mysql_password | the mysql user password | secret |
| mysql_user_host | where should this user be able to connect from | '%' | 
| mysql_host | the hostname of mysql | localhost |
| mysql_database | homestead | homestead |
| mysql_port | the port mysql should listen on | '3306' |
| mysql_bind_address | the ip address mysql is bound to | '0.0.0.0' |
| mysql_datadir | the path where mysql stores it's data | /var/lib/mysql |




