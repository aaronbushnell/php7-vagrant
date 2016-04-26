# PHP 7 Vagrant Box

A simple Vagrant setup using PHP 7, Apache, MySQL and Ubuntu.

## Requirements
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant](https://www.vagrantup.com/downloads.html)

## Installation
1. Clone this repo to your machine
2. Run `$ vagrant up` in the directory

## Quick Help

### Setting up new sites

```sh
# Edit the config file (using Sublime, but use whatever you want)
$ subl ~/Projects/PHP/puphpet/config.yaml

# Find the "vhosts" block under the "apache" section (not "ngnix")
# Copy one entire block that starts with a 12-character random ID
# Change the ID to another unique 12-character ID
# Provide a "servername", "docroot", and directories -> path that matches "docroot"

# Reload your Vagrant box with the new config settings
$ vagrant reload --provision

# Open up your computer's hosts file
$ subl /etc/hosts

# At the bottom of this file add in the newly created domain and your Vagrant IP. Swap "mysite.dev" with the value from "servername" in config.yaml
192.168.56.123 mysite.dev
```

### Connecting to MySQL from Sequel Pro

```
Type: SSH
MySQL Host: 192.168.56.123
Username: root
Password: vagrant

SSH Host: 192.168.56.123
SSH User: vagrant
SSH Key: click the key icon and then select puphpet/files/dot/ssh/id_rsa
```

### Quick Vagrant commands

```sh
# Checks the status of your Vagrant box (up, halted, suspended, etc)
$ vagrant status

# Resumes your Vagrant box from being halted, suspended, off
$ vagrant up

# Shuts down your Vagrant box
$ vagrant halt

# Shuts down your Vagrant box (if on) and restarts the box based on new config changes in config.yaml
$ vagrant reload --provision
```
