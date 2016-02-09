## Vagrant Ansible Postgres with PHP7

*I'm not sure why I didn't fork this from [Taytay/vagrant-ansible-postgres](https://github.com/Taytay/vagrant-ansible-postgres) but I didn't.. so there we go*  
*I changed a couple of things to update to PostgresSQL 9.5 and Ansible 2 but that's about it*

This uses Ansible to provision a Vagrant box with Postgres 9.5 and PHP7 for use with a a Symfony project.  
It optionally installs pgtap as well for use in testing your database configuration.  
Ansible will be installed on the Vagrant guest box and run from there.

I have used [this](https://github.com/Taytay/vagrant-ansible-postgres) for the PostgreSQL stuff.  
I've also used [this](https://atlas.hashicorp.com/peterrehm/boxes/symfony-php7) as the base box (includes the basic setup for Symfony with PHP 7).

###Everything that follows is form the original README.md (see [Taytay/vagrant-ansible-postgres](https://github.com/Taytay/vagrant-ansible-postgres))

## Requirements:

* Vagrant
* VirtualBox
* `nfsd` on the host, if host is Linux. (Hat tip to [davidemoro](https://github.com/Taytay/vagrant-ansible-postgres/issues/1))

## Usage

```
$ vagrant up
```

Your Vagrant box will now be running Postgresql, on localhost:5432.

The default user/password is: `pgsuper/password`

You can modify this and other playbook variables variables inside of `provisioning/group_vars/all`.

If you want to install [pgtap](http://pgtap.org/), which is helpful for unit testing your database, you can uncomment the pgtap role from the `playbook.yml` file.

Any time you make a change to the Ansible scripts and want to rerun provisioning:

```
$ vagrant provision
```

## License

I got almost everything in the playbook from [Taytay/vagrant-ansible-postgres](https://github.com/Taytay/vagrant-ansible-postgres)
who in turn (I quote) "got a lot of the playbook ideas and code from [Kami/ansible-postgresql](https://github.com/Kami/ansible-postgresql),
and as a result, this Playbook must be distributed under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html)".

