Ansible Role: MS Teams Notifier
=========

Ansible role to create notifications for an Microsoft Teams Channel via Webhooks.

Requirements
------------

The role does not require anything to run on Ubuntu, Debian or RHEL and its derivatives.

Role Variables
--------------

Available variables are listed below, along with default values (see ```defaults/main.yml```):

``` yaml
webhook: 'https://outlook.office.com/webhook/your_teams_webhook'
message_type: 'new-server'
```

```webhook:``` **(Required)** The Webhook created for the specified Teams Channel.
```message_type:``` **(Required)** The name of the JSON data template to use for the notification.

The existing options for ```message_type``` are:

- ```new-server:``` JSON formatted template for New Server build notifications

Role variables can be stored with the ```hosts.yaml``` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      tasks:
         - name: Some task
           ...
         - name: Send notification to MS Teams Channel
           ansible.builtin.import_role:
            name: mikepruett3.teams-notify
           vars:
            webhook: 'https://outlook.office.com/webhook/your_teams_webhook'
            message_type: 'new-server'
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-teams-notify)
