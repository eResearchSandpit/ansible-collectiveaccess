# Ansible provisioning for CollectiveAccess

[![Latest Version](https://img.shields.io/github/release/netsensei/ansible-collectiveaccess.svg?style=flat-square)](https://github.com/netsensei/ansible-collectiveaccess/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)

## Ansible provisioning for CollectiveAccess

This project provides [Ansible](http://www.ansible.com) provisinioning for easy/quick installation and configuration of a [CollectiveAccess](http://collectiveaccess.org/) instance.

### What is CollectiveAccess?

[CollectiveAccess](http://collectiveaccess.org/) is webbased software for describing all manner of things, and allows you to create catalogues that closely conform to your needs without custom programming.

### Requirements

You will need a working installation of [Ansible](http://www.ansible.com) on your machine and a remote server somewhere.  Currently the script only works for ubuntu VMs. Ubuntu instances on AWS work well.

### What is in the box?

- PHP 5.6 with a few required extensions
- MySQL database

## Install

Clone this repository to your local machine (we assume you have a dedicated workspace folder at `~/Workspace` refer to `Vagrantfile` to change this to a destination of your choice.)

```bash
cd ~/Workspace
git clone https://github.com/andre-geldenhuis/ansible-collectiveaccess
git checkout remote_server
```

### Setup hosts file

Create a keys directory and copy your SSH key there. If you are just using ansible to setup one server, you can create a hosts file to point at your remote server.  

#### hosts

```bash
[ca]
52.xx.xx.xx ansible_ssh_private_key_file=keys/yourSSHkey.pem
```

### Run the ansible playbook

Now, go back to the Ansible folder and run the playbook. Ansible should automatically start provisioning the box with all the necessary dependencies for CollectiveAccess.

```bash
ansible-playbook -i playbook.yml
```
## Usage

Open up your browser and navigate to either the IP address or domain of the remote server. First time, you will be welcomed by the Providence installer.

## Documentation

## Security

If you discover any security related, please email matthias@colada.be instead of using the issue tracker.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
