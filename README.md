# ansible-scout

Installs the agent for [Scout](http://scoutapp.com), a hosted server monitoring service, using [Ansible](https://github.com/ansible/ansible).

This playbook deploys the Scout agent on your hosts:

* Installs the [Scout Ruby gem](https://rubygems.org/gems/scout)
* Configures a Cron job to run the monitoring agent

## Supported Platforms

The following platforms are supported by this playblook, meaning that the playbook run on these platforms without error:

* Ubuntu
* Debian
* Red Hat
* CentOS
* Fedora

## Basic Setup

Provide your account key in the "scout_key" variable in `site.yml`, then:

	ansible-playbook site.yml

Or like this if you want to mention your host group on the command line:

	ansible-playbook -i hosts site.yml

See `hosts.sample.ini` for a sample inventory file w/Scout.

## Scout Roles

Scout configures monitoring by role names - these are specified via the `roles` variable name. You define monitoring roles in the Scout UI, then assign them in your inventory file. When a role is changed in the Scout UI, the monitoring configuration is immediately updated for all hosts with that role.

## Required Varibles

<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Description</th>
      <th>Default Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="width:15%">:scout_key</td>
      <td>
        The agent requires a Scout account and the account's associated key. The key can be found in the account settings tab within the Scout UI or in the server setup instructions. The key looks like:
          <code>0mZ6BD9DR0qyZjaBLCPZZWkW3n2Wn7DV9xp5gQPs</code> 
      </td>
      <td style="width:15%"><code>nil</code></td>
    </tr>
  </tbody>
</table>

## Optional Variables

<table>
  <thead>
    <tr>
      <th style="width:20%">Variable</th>
      <th>Description</th>
      <th>Default Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>:scout_user</td>
      <td>User to run the Scout agent under. Will be created if it does not exist.</td>
      <td><code>scout</code></td>
    </tr>
    <tr>
      <td>:name</td>
      <td>Optional name to display for this host within the Scout UI.</td>
      <td><code>nil</code></td>
    </tr>
        <tr>
      <td>:environment</td>
      <td>Optional environment to group this host under in the Scout UI.</td>
      <td><code>nil</code></td>
    </tr>
    <tr>
      <td>:roles</td>
      <td>A comma-separated list of roles for host node. Roles are defined through Scout's UI.</td>
      <td><code>nil</code></td>
    </tr>
  </tbody>
</table>

## Questions?

Contact Scout (<support@scoutapp.com>) with any questions, suggestions, bugs, etc.

## Authors and License

Additions, Modifications, & Updates:

Author: Derek Haynes (<support@scoutapp.com>)
Copyright: 2014, Scout
https://github.com/scoutapp/ansible-scout

Originally:

Author: Navid Paya
Copyright: 2014, Navid Paya
https://github.com/navidpaya/ansible-scout

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
