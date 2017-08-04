ansible-role-gremlin
=========

Ansible role to install [Gremlin Inc](https://gremlininc.com/)'s agent on Linux RedHat family operating systems.

Requirements
------------

- Ansible 2.3.1.0 (older versions yet to be tested)
- Gremlin account with organization ID and secret key

Role Variables and Default Values
--------------

- `gremlin_yum_repo_url=http://rpm.gremlininc.com/gremlin.repo`: url for Gremlin yum repo.
- `gremlin_docker_support=false`: adds gremlin user to docker group if `true`, Docker is therefore a dependency with this enabled.
- `gremlin_start_after_install=false`: runs the login and configure script during role execution if `true`. `false` is recommended if you are baking Gremlin using [Packer](https://www.packer.io/).
- `gremlin_org_id=""`: Gremlin organization ID.
- `gremlin_org_secret=""`: Gremlin organization secret key.
- `gremlin_service_name=""`: service or group name that groups hosts in Gremlin's dashboard.
- `gremlin_host_identifier="{{ ansible_hostname }}"`: name for your host that defaults to hostname as seen by Ansible.

Dependencies
------------

If you want to use Gremlin's Docker attacks, and you set `gremlin_docker_support=true`, then you will need to have Docker installed prior to running this role. Otherwise, there are no role dependencies.

_Note: the role does require [privilege escalation](http://docs.ansible.com/ansible/latest/become.html) (e.g. `become`) since it deals with adding a repo and installing packages._

Example Playbook
----------------

    # Example passing in org ID and secret as role variables
    - hosts: servers
      roles:
         - { role: gremlin, gremlin_org_id: foo, gremlin_org_secret: bar, gremlin_service_name: api }

    # This example you could pass in the org ID and secret via Ansible's --extra-vars at runtime
    # Also an example of overriding gremlin_host_identifer with a command that would be helpful if running in AWS and you're using this role with Packer's Ansible provisioner
    - hosts: servers
      roles:
        - role: examsoft-gremlin
          gremlin_docker_support: true
          gremlin_service_name: reporting
          gremlin_host_identifier: "$(curl http://169.254.169.254/latest/meta-data/instance-id)"


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
