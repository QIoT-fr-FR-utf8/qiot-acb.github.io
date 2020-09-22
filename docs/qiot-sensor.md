# QIoT Sensor

### Build process

1. Checkout code
1. Build image 
1. Login to Quay.io
1. Push to Quay!

````
$ git clone https://github.com/ACB-FR/qiot-sensor-py
$ cd qiot-sensor-py
$ sudo podman build -t quay.io/acb-fr/qiot-sensor -t quay.io/acb-fr/qiot-sensor:1-aarch64 -t quay.io/acb-fr/qiot-sensor:1.0.3 .
$ sudo podman login
$ sudo podman push quay.io/acb-fr/qiot-sensor:1.0.3
```

Note: podman commands are run in sudo mode, as the container runs in privileged mode, and it's easier for that PoC to build and run container as root.

### Start Container

Once the container is built, run it!

```
$ sudo podman run -d --network=qiot --privileged -p 8000:8000 --name qiot-sensor quay.io/acb-fr/qiot-sensor:1.0.3
```
