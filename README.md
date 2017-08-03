ansible-role-gremlin
=========

Ansible role to install [Gremlin Inc](https://gremlininc.com/)'s Agent on Linux RedHat family operating systems.

Requirements
------------

- >= Ansible 2.3.1.0
- Gremlin API key

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

- `variable-key`: default_value
- `gremlin-api-key`: ""
- `gremlin-repo-url`: http://rpm.gremlininc.com/gremlin.repo

Dependencies
------------

There are no role dependencies.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: gremlin, gremlin-api-key: 1234-1234-1234-1234 }

Contribution
------------

Improvement and help maintaining this is always welcome. Open issues, fork and create PRs, I'll do my best to respond/reply in a timely manner.

License
-------

[MIT License](https://choosealicense.com/licenses/mit/)

Author Information
------------------

John Paul Herold
[Twitter](https://twitter.com/dailyherold)
