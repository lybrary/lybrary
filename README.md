# Team

[![wercker status](https://app.wercker.com/status/616ceedd54f9bafa1e1529308ba514e9/m/master "wercker status")](https://app.wercker.com/project/byKey/616ceedd54f9bafa1e1529308ba514e9)

## Project Installation

### Requirements

* Vagrant for VM management
* Ansible for VM provisioning

### Vagrant setup steps

* `ansible-galaxy install -r requirements.yml` - Install the required ansible-galaxy roles.
* `vagrant up` - Bring up the vagrant box

_**Warning:** some default credentials for MySQL are stored in the Ansible provisioning files. These are not secure and should only be used for development purposes on a secured machine and throwaway VM. Do not use them for production values!_

### Run the server
* Set the following environment variables to their values for a MySQL database. If you're using Vagrant, this step can be ignored.

```
DB_HOST
DB_USER
DB_PASS
DB_PORT
```

* `bundle install` will install package dependencies.
* `rails db:setup && rails db:migrate` to setup the database.
* `rails s -b 0.0.0.0` will set it running on port 3000 in the vagrant box. You can then access it from `http://192.168.33.8:3000/` on your browser.
