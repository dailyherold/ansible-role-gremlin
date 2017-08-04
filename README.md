ansible-role-gremlin
=========

Ansible role to install [Gremlin Inc](https://gremlininc.com/)'s agent on Linux RedHat family operating systems.

Requirements
------------

- Ansible 2.3.1.0 or newer
- Gremlin API key

Role Variables
--------------

Variables and default values:

- `gremlin-yum-repo-url`: http://rpm.gremlininc.com/gremlin.repo
- `gremlin-docker-support`: false
- `gremlin-org-id`: ""
- `gremlin-org-secret`: ""
- `gremlin-host-identifier`: ""
- `gremlin-service-name`: ""
- `gremlin-start-after-install`: false

Dependencies
------------

There are no role dependencies to run this one. It _does_ require `become` however since a repo and packages are installed.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: gremlin, gremlin-api-key: 1234-1234-1234-1234-1234 }

Contribution
------------

Help maintaining this repo is always welcome. Open issues, fork and create PRs, I'll do my best to respond/reply in a timely manner.

License
-------

[MIT License](https://choosealicense.com/licenses/mit/)

Author Information
------------------

John Paul Herold
[Twitter](https://twitter.com/dailyherold)
