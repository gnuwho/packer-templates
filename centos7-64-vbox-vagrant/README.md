centos7-64-vbox-vagrant
=======================

This builds a basic 64-bit CentOS 7 Vagrant box for VirtualBox with the vagrant user. Steps are taken to minimize the size of the resulting image.

## Note
Even though `bzip2` is installed during the build process, shared folders may not work on the resulting image until `bzip2` is installed.

A `vagrant up` will result in the following error:

```
Failed to mount folders in Linux guest. This is usually because
the "vboxsf" file system is not available. Please verify that
the guest additions are properly installed in the guest and
can work properly. The command attempted was:

mount -t vboxsf -o uid=`id -u vagrant`,gid=`getent group vagrant | cut -d: -f3` vagrant /vagrant
mount -t vboxsf -o uid=`id -u vagrant`,gid=`id -g vagrant` vagrant /vagrant

The error output from the last command was:

mount: unknown filesystem type 'vboxsf'
```

During the build process, the install `bzip2` step will show the following:

```
   virtualbox-iso: ---> Package bzip2.x86_64 0:1.0.6-12.el7 will be installed
   virtualbox-iso: --> Finished Dependency Resolution
   virtualbox-iso:
   virtualbox-iso: Dependencies Resolved
   virtualbox-iso:
   virtualbox-iso: ================================================================================
   virtualbox-iso: Package         Arch             Version                  Repository      Size
   virtualbox-iso: ================================================================================
   virtualbox-iso: Installing:
   virtualbox-iso: bzip2           x86_64           1.0.6-12.el7             base            52 k
   virtualbox-iso:
   virtualbox-iso: Transaction Summary
   virtualbox-iso: ================================================================================
   virtualbox-iso: Install  1 Package
   virtualbox-iso:
   virtualbox-iso: Total download size: 52 k
   virtualbox-iso: Installed size: 86 k
   virtualbox-iso: Downloading packages:
   virtualbox-iso: Running transaction check
   virtualbox-iso: Running transaction test
   virtualbox-iso: Transaction test succeeded
   virtualbox-iso: Running transaction
   virtualbox-iso: Installing : bzip2-1.0.6-12.el7.x86_64                                    1/1
   virtualbox-iso: Verifying  : bzip2-1.0.6-12.el7.x86_64                                    1/1
   virtualbox-iso:
   virtualbox-iso: Installed:
   virtualbox-iso: bzip2.x86_64 0:1.0.6-12.el7
   virtualbox-iso:
   virtualbox-iso: Complete!
```

Please install `bzip2` with:

    yum install -y bzip2
    
and restart the box.
