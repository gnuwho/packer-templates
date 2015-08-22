# jessie-64-vbox-vagrant
This is a [Packer](https://packer.io) template for building an basic Debian Jessie amd64 image using the `virtualbox-iso` builder, the `shell` provisioner, and the `vagrant` post-processor.

This template was generated using [Rancher](https://github.com/mohae/rancher) and my [rancher-templates](https://github.com/mohae/rancher-templates) repository.

The point release of Jessie that is used will be the one that was current at the time of template generation. If there is a more recent point release, please file an issue. 

You can also generate an updated template by using Rancher and the appropriate Rancher template.

## Usage
Create the artifact:

    packer build jessie-64-vbox-vagrant

Start with [Vagrant](https://vagrantup.com):

    vagrant up

## Vagrantfile
A basic `Vagrantfile` is included. 

Or you can generate a new one by:
 
    vagrant init jessie-64-vbox-vagrant

This image uses 1024MB of RAM. If this is too much or too little, modify it in the `Vagrantfile`:

    config.vm.provider "virtualbox" do |v|
      vb.memory = "512"
    end  

To sync a folder between the host machine and the guest, uncomment the `config.vm.synced_folder` setting and set to the appropriate values.

For a complete reference, please see the online documentation at https://docs.vagrantup.com/v2.