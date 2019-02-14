netbox-app
=========

Ensures that the [NetBox](http://netbox.readthedocs.io/) application is installed and running.

Role Variables
--------------

  - `netbox_install_directory`: /opt
  - `netbox_database_name`: The database name
  - `netbox_database_user`: Username to connect to the database with
  - `netbox_database_password`: Password for the database user
  - `netbox_allowed_hosts`: ['localhost']
  - python_command: specify the python executable for the virtualenv

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - name: netbox-app
          netbox_install_directory: /srv
          netbox_database_name: netbox_db_name
          netbox_database_user: username
          netbox_database_password: p@$$w0rd
          netbox_allowed_hosts:
            - "localhost"
            - "localhost:20443" # workaround for CSRF protection
                                # when running on a non-standard port
                                # for development or testing

Dependencies
------------

Requires a PostgreSQL database. This can be installed with the `netbox-db` role:

```
$ ansible-galaxy install straylight-project.netbox-db
```

License
-------

Apache 2.0
