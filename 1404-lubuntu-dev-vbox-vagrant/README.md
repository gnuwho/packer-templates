# 1404-lubuntu-dev-vbox-vagrant
This is a [Packer](https://packer.io) template for building an Ubuntu LTS 14.04 amd64 lubuntu desktop image using the `virtualbox-iso` builder, the `shell` provisioner, and the `vagrant` post-processor with some languages and editors installed.

This template was generated using [Rancher](https://github.com/mohae/rancher) and my [rancher-templates](https://github.com/mohae/rancher-templates) repository.

The point release of 14.04 that is used will be the one that was current at the time of template generation. 

You can also generate an updated template by using Rancher and the appropriate Rancher template.

## Usage
Create the artifact:

    packer build 1404-lubuntu-dev-vbox-vagrant

Start with [vagrant](https://vagrantup.com):

    vagrant up

## Vagrantfile
A basic `Vagrantfile` is included with minimal settings.

The `vm.synced_folder` is set to share the host machine's `../data` as the guest machine's `/vagrant_data`.

This image uses 2048MB of RAM. If this is too much or too little, modify it in the `Vagrantfile`:

    config.vm.provider "virtualbox" do |v|
      vb.gui = true
      vb.memory = "512"
    end  

This image also has 128MB of video memory and 3D accelaration enabled. This can be modified in the `config.vm.provider` section too.
 
Since this is a desktop image, Vagrant's `vb.gui` setting is set to `true`.

For a complete reference, please see the online documentation at https://docs.vagrantup.com.

## Installed software
This is only the software explicitely installed by this template. Unless noted otherwise, it does not include any software that is already installed by the distro or `lubuntu`.  

### General
```  
* bzip
* curl
* git
* rsync
* tree
* wget  
```

### Browsers
This list includes browsers that come with the distro.
```  
* Chrome
* Chromium
* Firefox
```  

### Editors
```  
* atom
* emacs
* vim  
```  

### Languages
This list includes languages that come with the distro.
```
* C
* C++
* Dart
* Go
* Java
* Lua
* Perl
* Python
* Rust
``` 
