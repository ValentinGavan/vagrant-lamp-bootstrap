# vagrant-lamp-bootstrap

A super-simple Vagrantfile / bootstrap.sh to setup a LAMP stack inside Vagrant 100% automatically.

### What it contains

This is a reduced-to-the-max Vagrant setup file for a quick development stack. It will:

* setup a Ubuntu 16.04 LTS "Xenial Xerus" 64bit box

* make the box accessible by the host at IP `192.168.33.22` or allow the IP to be assigned via DHCP.

* sync the current folder with `/var/www/html` inside the box

* automatically perform all the commands in bootstrap.sh directly after setting up the box for the first time

The bootstrap.sh will:

* update, upgrade

* create a folder inside /var/www/html

* install apache 2.4, php 7, MySQL, PHPMyAdmin, git and Composer

* set a pre-chosen password for MySQL and PHPMyAdmin

* activate mod_rewrite and add *AllowOverride All* to the vhost settings

You can update folder and password inside the bootstrap.sh

### Usage

Put `Vagrantfile` and `bootstrap.sh` inside a folder and do a `vagrant up` on the command line.
This box uses Ubuntu 16.04 LTS "Xenial Xerus" 64bit, so if you don't have the basic box already, do a
`vagrant box add ubuntu/xenial64` before.

### Behind proxy ?

Update proxy settings in Vagranfile accordingly and install vagrant-proxyconf

`vagrant plugin install vagrant-proxyconf`
