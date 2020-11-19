philranzato.docker-ce
=========

[![Build Status](https://travis-ci.com/PhilRanzato/philranzato.docker-ce.svg?token=ZNaPXzqK9QuDLLygA1WH&branch=feature-GH19-TravisCI)](https://travis-ci.com/PhilRanzato/philranzato.docker-ce)

Install and manage Docker CE on multiple OS.

Requirements
------------

- Internet connection.
- Sudo permissions for the user that runs ansible.

Role Variables
--------------

```yaml
---
docker:
  # The username to add to the docker group
  user: "foo"
  # Do not specify version if you want the latest
  version: "19.03.13"
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
# Install docker-ce version 19.03.13 and add ansible user to docker group
- name: "Install docker-ce"
  hosts: servers
  roles:
  - role: philranzato.docker-ce
  vars:
    docker:
      user: "ansible"
      version: "19.03.12"

# Install docker-ce version latest not adding any user to the docker group
- name: "Install docker-ce"
  hosts: servers
  roles:
  - role: philranzato.docker-ce
  vars:
    # set docker variable to override defaults
    docker:

# Install docker-ce version latest and add user foo to the docker group
- name: "Install docker-ce"
  hosts: servers
  roles:
  - role: philranzato.docker-ce
  vars:
    docker:
      user: "foo"
```

License
-------

MIT License

Author Information
------------------

Get in touch with me at:
- [LinkedIn](www.linkedin.com/in/phil-ranzato-47b8bb194)
- [GitHub](https://github.com/PhilRanzato)
- [Medium](https://medium.com/@philranzato)
