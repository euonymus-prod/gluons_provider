# Requirement

* Vagrant
* Chef
* knife-solo
* Berkshelf
* vagrant-digitalocean
* digital_ocean.box
* vagrant-omnibus


# Prepare following files as git submodules

    $ git submodule init
    $ git submodule update

* src/lampapp
* src/secrets
* chef
* chef/site-cookbooks/lamp
* chef/site-cookbooks/cakephp
* chef/site-cookbooks/gluons

# gluons_provider
place your own /src/hosts/host_settings.rb file with following format

    TOKEN = '{YOUR_PRIVATE_KEY_TO_DIGITALOCEAN}'
    HOSTNAME = '{some-host-name}'
    USERNAME = '{some_user_name}'
    CHEF_ENVIRONMENT = 'production'
    PRIVATE_KEY_PATH = '~/.ssh/id_rsa'
    SSH_KEYNAME = '{YOUR_SSH_KEYNAME_ON_DIGITALOCEAN}'

* src/hosts

# Prepare chef

    $ cd {path_to_this_repo}/chef
    $ git checkout master
    $ berks vendor cookbooks
    $ git submodule init
    $ git submodule update

# Prepare cookbooks

    $ cd {path_to_this_repo}/chef/site-cookbooks/lamp
    $ git checkout master
    $ cd {path_to_this_repo}/chef/site-cookbooks/cakephp
    $ git checkout master


# Prepare the secrets' submodules

    $ cd {path_to_this_repo}/src/lampapp
    $ git checkout master

# Prepare the application's submodules

    $ cd {path_to_this_repo}/src/lampapp
    $ git checkout master

# Prepare the application source

    $ cd {path_to_this_repo}/src/lampapp
    $ composer install

