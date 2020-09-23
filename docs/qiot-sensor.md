# QIoT Sensor

## Implementation

## Issues, Ideas

## Annexes

### Build process

1. Checkout code
1. Build image 
1. Login to Quay.io
1. Push to Quay!

```
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

Make it restart automatically on boot with systemd:

1. Generate systemd file
1. Modify to comply with new linux tree `/run`
1. Copy and activate service

```
$ sudo podman generate systemd --name qiot-sensor > podman-qiot-sensor.service
$ vi podman-qiot-sensor.service
PIDFile=/run/containers/storage/overlay-containers/[...]/userdata/conmon.pid
$ sudo systemctl daemon-reload
$ sudo systemctl enable podman-qiot-sensor
$ sudo systemctl start podman-qiot-sensor.service
```

1. Check it runs!
```
$ sudo systemctl status podman-qiot-sensor.service
● podman-qiot-sensor.service - Podman container-qiot-sensor.service
   Loaded: loaded (/etc/systemd/system/podman-qiot-sensor.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2020-09-22 19:24:41 UTC; 5min ago
     Docs: man:podman-generate-systemd(1)
 Main PID: 97930 (conmon)
    Tasks: 3 (limit: 997)
   Memory: 3.4M
      CPU: 1.940s
   CGroup: /system.slice/podman-qiot-sensor.service
           ├─97928 /usr/sbin/dnsmasq -u root --conf-file=/run/containers/cni/dnsname/qiot/dnsmasq.conf
           └─97930 /usr/bin/conmon --api-version 1 -s -c 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d -u 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d -r /usr/bin>

Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using local addresses only for domain dns.podman
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: reading /etc/resolv.conf
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using local addresses only for domain dns.podman
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using nameserver 192.168.1.10#53
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: using nameserver 192.168.1.254#53
Sep 22 19:24:41 qiot.verchere.lab dnsmasq[97928]: read /run/containers/cni/dnsname/qiot/addnhosts - 1 addresses
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: 2020-09-22 19:24:41.29127181 +0000 UTC m=+1.755286386 container init 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d (image=quay.io/acb>
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: 2020-09-22 19:24:41.336614494 +0000 UTC m=+1.800629071 container start 8ffb54b96b1abf4b9d1144d5458a72dd20cd51c0b9b4f64134670d32d5cfad8d (image=quay.io/a>
Sep 22 19:24:41 qiot.verchere.lab podman[97782]: qiot-sensor
Sep 22 19:24:41 qiot.verchere.lab systemd[1]: Started Podman container-qiot-sensor.service.
```
