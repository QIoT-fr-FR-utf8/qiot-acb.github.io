# Using aarch64 VM

* TOC
{:toc}

## Implementation

Using it to build Quarkus application in native mode, and also automate the docker build image process.

## Annexes

### Init

```
$ wget https://dl.fedoraproject.org/pub/fedora/linux/releases/32/Workstation/aarch64/images/Fedora-Workstation-32-1.6.aarch64.raw.xz
$ unxz Fedora-Workstation-32-1.6.aarch64.raw.xz
$ virt-sysprep -a Fedora-Workstation-32-1.6.aarch64.raw --enable password --root-password password:fedora
```

### Create Virtual Machine

Using "Virtual Machine Manager", create a new machine with the following settings:
* Import existing disk image
* Architecture options
 * Architecture `aarch64`
 * Machine type `virt`
* Select `Fedora-Workstation-32-1.6.aarch64.raw` as disk image
* Update CPUs and RAM settings
* Boot!

### Install GraalVM

* Update and install dependencies

```
# dnf update
# dnf -y install gcc glibc-devel zlib-devel libstdc++-static
# dnf -y install java-11-openjdk
# wget https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-20.2.0/graalvm-ce-java11-linux-aarch64-20.2.0.tar.gz
# tar zxvf graalvm-ce-java11-linux-aarch64-20.2.0.tar.gz
# mkdir /usr/lib/graalvm
# mv graalvm-ce-java11-20.2.0 /usr/lib/graalvm
```

* Update PATH, editing `/etc/profile`:

```
[...]
GRAALVM_HOME=/usr/lib/graalvm/graalvm-ce-java11-20.2.0
JAVA_HOME=$GRAALVM_HOME
export GRAALVM_HOME

PATH=$PATH:$HOME/bin:$GRAALVM_HOME/bin
export PATH
```

### Build Application

```
# git clone https://github.com/QIoT-fr-FR-utf8/qiot-edge-service.git
# cd qiot-edge-service/
# gu install native-image # Do only once to ged native-image
# ./mvnw package -Pnative
```

### Generate container

```
# podman login quay.io
# podman build -f src/main/docker/Dockerfile.native -t quay.io/acb-fr/qiot-edge-service:1-aarch64 .
# podman push quay.io/acb-fr/qiot-edge-service:1-aarch64
```
