## Deploying [Scout Client](https://github.com/scoutapp/scout-client) Using [Ansible](https://github.com/ansible/ansible)

- Requires Ansible on your control node
- Has been tested with Debian 7 and CentOS 6 but should work on most similar distros

This playbook deploys the Scout client on your servers.
You just need to pass a host or a host group to it. Take a look
at the sample hosts.ini to get an idea. Also make sure you adjust
the site.yml file to your needs. You just need to run it like this:

	ansible-playbook site.yml

Or like this if you want to mention your host group on the command line:

	ansible-playbook -i hosts site.yml

## Problem or Questions?

You can open an issue and I'll do my best to get back to you ASAP.
