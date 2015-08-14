# packer-templates
This repo contains templates for [Packer](https://packer.io). 

These templates were generated using [Rancher](https://github.com/mohae/rancher).

Please see each template for details.

## Prerequisites
[Packer](https://packer.io) must be installed to use these templates.

Any other software that the templates depend on must also be installed: e.g. for templates using the `virtualbox-iso` provisioner, you must have [Virtualbox](https://www.virtualbox.iso) installed.

## Usage
Copy the repository:

    git clone https://github.com/mohae/packer-templates

Create the desired artifact:

    cd packer-templates ubuntu-64-vbox-vagrant
    packer build ubuntu-64-vbox-vagrant.json

## Notes
These templates break [Vagrant](https://vagrantup.com) conventions for hostname and RAM. The template name is used as the host name for the box it creates. Instead of 512MB of ram, these boxes start with 1024MB. 