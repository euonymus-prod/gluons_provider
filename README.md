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
    HOSTNAME = 'gluons-prod1'
    CHEF_ENVIRONMENT = 'production'
    PRIVATE_KEY_PATH = '~/.ssh/id_rsa'
    SSH_KEYNAME = '{YOUR_SSH_KEYNAME_ON_DIGITALOCEAN}'

* src/hosts

# Prepare cookbooks

    $ cd {path_to_this_repo}/chef
    $ berks vendor cookbooks

# Prepare the application's submodules

    $ cd {path_to_this_repo}/src/lampapp
    $ git checkout master
    $ git submodule init
    $ git submodule update

# Prepare the application source

    $ cd {path_to_this_repo}/src/lampapp
    $ composer install

