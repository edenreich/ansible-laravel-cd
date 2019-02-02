<p align="center"><img src="https://drive.google.com/uc?export=view&id=1XQqfsu4RAHHjxzmjEFP3zdtyPOvFpLLr"></p>

# Ansible Zero Downtimes

Continuous delivery with zero downtime setup, very simple to use.

A simple setup to get up and running with:
- nginx
- php7.1-fpm
- mysql-server

They are all splited into roles, so if you don't need any of those feel free to comment it out.

## Requirements

Ansible

## Configurations

- Add server addresses to the hosts file
- Configure /group_vars/all.yml with your info

## Options

| Option Name  | Description |
| ------------- | ------------- |
| projects_root  | the directory where all of the websites are located (e.g /var/www)  |
| project_name  | the project name, ansible will create a folder with that name  |
| repository  | the link to your git repository  |
| releases_to_keep  | how many releases should be kept ?  |
| ssh_key  | the path to your ssh key  |
| mysql_username  | the mysql username  |
| mysql_root_password  | the mysql password |

## Usage

To deploy run:
```sh
ansible-playbook deploy.yml
```

To rollback to a previous release run:
```sh
ansible-playbook rollback.yml
```
