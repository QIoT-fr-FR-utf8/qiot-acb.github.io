# Using aarch64 VM

Using it to build Quarkus application in native mode, and also automate the docker build image process

## Init

```
$ wget https://dl.fedoraproject.org/pub/fedora/linux/releases/32/Workstation/aarch64/images/Fedora-Workstation-32-1.6.aarch64.raw.xz
$ unxz Fedora-Workstation-32-1.6.aarch64.raw.xz
$ virt-sysprep -a Fedora-Workstation-32-1.6.aarch64.raw --enable password --root-password password:fedora
```

## Create Virtual Machine

Using "Virtual Machine Manager", create a new machine with the following settings:
* Import existing disk image
* Architecture options
 * Architecture `aarch64`
 * Machine type `virt`
 
 
