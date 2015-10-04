jessie-chef-solo-vbox-vagrant
===========================

This template creates a Debian Jessiegit vagrant box for with `chef-solo` installed.

The purpose of this Packer template is to create a development box with Chef Solo already installed to aid in either the learning of Chef Solo or the development of Chef artifacts.

The `vagrant` user is used to install Chef Solo; it is not under `root`.

There is an empty `chef-solo` directory that is shared as `/home/vagrant/chef-solo` in the virtual machine. Anything created in here will remain on the host. Any file or directory that exists in this directory, on the host, will exist in the VM.

The VM is configured with 2048 MB of RAM to prevent memory exhaustion during the compile of Gems.
