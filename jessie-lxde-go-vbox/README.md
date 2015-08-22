# jessie-lxde-go-vbox
This is a [Packer](https://packer.io) template for building a Debian 8 (jessie) lxde desktop image with stuff for Go development using the `virtualbox-iso` builder and the `shell` provisioner.

Currently, using the `vagrant` post-processor causes the resulting box to not use a desktop. As such this was excluded. 

This template was generated using [Rancher](https://github.com/mohae/rancher) and my [rancher-templates](https://github.com/mohae/rancher-templates) repository.

At time of template generation 8.1 was the current release.

## Usage
Create the artifact:

    packer build jessie-lxde-go-vbox

### Virtualbox
The resulting image is an `ovf` file. Using Virtualbox, import the `jessie-lxde-go-vbox.ovf` file. After import, start the VM.

Any adjustments to the resources allocated to the VM will have to be done through VirtualBox.

## Installed software
This is only the software explicitly installed by this template. Unless noted otherwise, it does not include any software that is already installed by the distro or `lubuntu`.  

### General
```  
* bzip2
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
* liteide
* vim  
```  

#### `vim`
`vim` is installed with [spf13's vim distribution](vim.spf13.vim). [Fatih's go-vim](https://github.com/fatih/vim-go) plugin is installed.

When first using `vim`, you must run `:GoInstallBinaries` command from within `vim`. 

#### `liteide`
[Liteide](https://github.com/visualfc/liteide) is an ide for Go.

## Go
Go is installed using the compiled tarball that Go provides and is installed to `\usr\local\go`. 

### PATH
`\usr\local\go\bin` has been added to the Vagrant user's PATH. 

#### GOPATH
The `GOPATH` is set to `/home/vagrant/code/go`. 

#### `delve`
For debugging, Derek Parker's [delve](https://github.com/derekparker/delve) has been installed.

For more information about Go, please go to the [Go website](https://golang.org).

