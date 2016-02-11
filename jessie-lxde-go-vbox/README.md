jessie-lxde-go-vbox
===================
A [Packer](https://packer.io) template to build a Jessie based box with the lxde desktop, Go, Go related tools, and some additional tools installed.

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
### Go related:

* [Go](https://golang.org) (latest release)
* [delve](https://github.com/derekparker/delve) (A Go debugger)
* [liteide](https://github.com/visualfc/liteide) (A Go ide)

### Installed editors:
In addition to LiteIDE:

* atom
* emacs
* vim w spf13-vim

** Installed software
In addition to what comes with LXDE:

* alsa-utils
* build-essential
* bzip2
* chrome
* chromium
* curl
* dkms
* git
* konsole
* liblz4-tool
* linux-headers-$(uname -r)
* quassel
* rsync
* tree
* wget

## Removed Software
*  xscreensaver

## Notes
### Timezone
Timezone is set to America/Chicago; to change the timezone, modify the `shell/timezone` shell script.

### User
The initial user is `vagrant`.  To change it, modify the `http/preseed.cfg` file.  The `shell\vagrant_user` file does additional configuration of this user.  Update accordingly.  It also sets the `.ssh\authorized_key` to Vagran'ts insecure public key.  Modify to suit your needs.

### Audio
The audio is set to use `dsound` (Windows direct sound) and `ac97` as the audio controller.  If you have a non-Windows host, you may need to change this.  A list of valid `VBOXMANAGE modifyvm` settings, for VirtualBox 5, and their possible values can be found at https://gist.github.com/mohae/2693378ce107dfa3eabf.

To get sound working: 

    $ /usr/sbin/alsactl init
    Found hardware: ... // hardware information
    Hardware is initialized using a generic method
    
or
 
    $ sudo su
    # alsactl init
    Found hardware: ... // hardware information
    Hardware is initialized using a generic method
    # exit
    $
    
    
