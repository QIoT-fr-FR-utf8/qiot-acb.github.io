# Fedora IoT

* TOC
{:toc}

## Implementation

One of the main goal of this projet is to use a maximum of Red Hat technologies.

Red Hat offers a Fedora distribution dedicated for IoT : [Fedora IoT](https://iot.fedoraproject.org/).

![Fedora IoT Logo](img/fedora-logo.png)

The main characteristics of that distribution are:

* Aarch64 distribution for Raspberry Pi
* Atomic updates, managed by `rpm-ostree`, a hybrid image.package system
* Podman to run applications

Then, all the code provided for that project must run in container, and we should avoid install packages directly with `rpm-ostree`.

## Issues, Ideas

### Operating System

We faced some issues to make the Operating System correctly with the RPi + Enviro+ board:

1. You need to change the `uboot` parameters at boot, and you need keyboard+screen to do that. This is sad for an IoT device :/
1. You need to install and configure `i2c-tools` ON THE host device, to make it accessible from the containers
1. The last but not the least, every documentation and how-to you find on the Internet is based on *Raspbian*!

Thanks to the weekly Drop'In Clinic, we managed to make it works.

### CI/CD

We also tried to use some CI to automatically build the images, using github actions (as the code is hosted on Github, you know), but:

* github does not provide (yet) aarch64 architecture on their runners
* we tried to setup local runners on [aarch64-vm](aarch64-vm.md), but the setup could not complete.

### Security

1. We should not disable SELinux
1. We should not disable firewalld

### Others

After that, as the team is mainly ops and sysadmins, using Feodra on their personnal workstations (and not a beautiful Macbook Pro like yours maybe, reading these lines!) no specific difficulties to make podman and other stuff work.
