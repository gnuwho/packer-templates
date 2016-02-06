# packer-templates
This repository contains [Packer](https://packer.io) templates. 

The templates were generated using [Rancher](https://github.com/mohae/rancher) and the [rancher-templates repository](https://github.com/moahe/rancher-templates).

Each directory contains a template to build an artifact with Packer.  At minimum, the name describes the guest OS, the Packer builder, and the Packer post-processor used by the build template.

Please see each template for details.

## Prerequisites
[Packer](https://packer.io) must be installed to use these templates.

Any other software that the templates depend on must also be installed: e.g. for templates using the `virtualbox-iso` provisioner, you must have [Virtualbox](https://www.virtualbox.iso) installed.

## Usage
Copy the repository:

    git clone https://github.com/mohae/packer-templates

Create the desired artifact:

    cd packer-templates/1404-64-vbox-vagrant
    packer build 1404-64-vbox-vagrant.json

## Vagrant
For templates that use the [Vagrant](https://vagrantup.com) post-processor, a simple Vagrantfile is included. 

If you wish to sync folders between the Host machine and the Guest, uncomment the `config.vm.synced_folder` setting and set appropriately. By default this setting has bee configured to shares the hosts `../data` directory with the guest's `/vagrant_data`.

For desktop images the `vb.gui` setting has been set to `true`; otherwise the value is set to `false`. 

Please refer to [Vagrant's documentation](https://docs.vagrantup.com/v2/) for more information. 

## Notes
These templates break [Vagrant](https://vagrantup.com) conventions for hostname and RAM. The template name is used as the host name for the box it creates. Instead of 512MB of RAM, these boxes start with 1024MB; desktop images are configured with 2048MB of RAM, 128MB of VRAM, and with 3D accelaration enabled.

Please refer to each Packer template's `README`, if there is one, for more specific information about that particular template.
