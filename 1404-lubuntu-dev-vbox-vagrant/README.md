1404-lubuntu-dev-vbox-vagrant
===================
A [Packer](https://packer.io) template to build an Ubuntu 14.04 LTS based Lubuntu desktop box with some programming languages and additional software.  A server image is used as the basis for this VM.

The resulting image will be configured with:

* 1 cpu
* 2048 RAM
* 128 VRAM
* 3d acceleration enabled
* bidirectional clipboard
* audio dsound
* audiocontroller ac97

To change the VM configuration, modify or delete the relevant `modifyvm` setting in the Packer template.

## Installed Software
### Languages:
In addition to the languages that come with the distro:

* Go (latest release)
* Dart (latest stable release)
* Java (apt)
* lua 5.2
* Rust (via rustup.sh)
* TypeScript (npm)

### Installed editors:

* atom
* emacs
* vim w spf13-vim

## Additional software and packages
In addition to what comes with Lubuntu:

* alsa-utils
* build-essential
* bzip2
* chrome
* chromium
* curl
* dkms
* gettext
* git
* konsole
* libexpat1-dev
* libcurl4-gnutls-dev
* libssl-dev
* linux-headers-$(uname -r)
* quassel
* rsync
* transport-https
* tree
* wget

## Notes
### Timezone
Timezone is set to America/Chicago; to change the timezone, modify the `shell/timezone` shell script.

### User
The initial user is `vagrant`.  To change it, modify the `http/preseed.cfg` file.  The `shell\vagrant_user` file does additional configuration of this user.  Update accordingly.  It also sets the `.ssh\authorized_key` to Vagran'ts insecure public key.  Modify to suit your needs.
    
