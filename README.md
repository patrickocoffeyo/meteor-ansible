# Meteor Ansible Scripts
This repository contains Ansible-based tools for:

* Provisioning GNU+Linux-based servers with dependencies needed to run Meteor.
* Building and running a Meteor application on a set of servers.

## Installation
* Install [Ansible](http://docs.ansible.com/ansible/intro_installation.html).
* Install Ansible dependencies:
  * `ansible-galaxy install carlos.acp.meteor`
  * `ansible-galaxy install geerlingguy.nodejs`
* Clone this repository.

## Configuration
* Copy `hosts.example` to `hosts`, and create records of all servers to which your Meteor app should be deployed.
* Edit `vars/main.yml` and adjust the following values:
  * meteor_project_git
  * meteor_project_version
  * meteor_version

## Use
* To provision a server, run: `ansible-playbook -i hosts tasks/provision.yml`
* To build, deploy, and run the Meteor app specified in `vars/main.yml`, run: `ansible-playbook -i hosts tasks/deploy.yml`

