# Quarkus for IoT Hackfest

![quarkus](img/quarkus.png)

* TOC
{:toc}

## Introduction

The QIoT project is designed for EMEA App Dev partners interested in new Red Hat Cloud-Native Technologies and Edge Architecture design and implementation

EMEA App Dev Partners join the project participating in a Hackfest, a challenge for Partners to implement a real-world use-case scenario.

[Axians Cloud Builder](https://www.axians.fr), as a French Red Hat Partner, participates to this hackfest.

This challenge was done in September 2020, in France, Earth, during our free time (almost).

You will find below some documentation about that challenge.

Happy hacking!

## The team

We are the "Axians Cloud Builder" France team, with:

* David Auffray - Twitter: [@DavAuff](https://twitter.com/DavAuff) - Github : https://github.com/Davidffry
* Sébastien Davoult
* Jérémy Hoarau
* Chamseddine Saadoune
* Rémi Verchère

See [team organization](organization.md) to see how we worked on the project.

## Technical choices

Hereafter some technical details about our work, choices, issues, solutions and other things we faced.

All subpages are divided in paragraphs:

1. Implementation, to give some information on the technical part (goal, environment, how we did things)
1. Issues and ideas, to show problems we faced, and some ideas for a future work
1. Annexes, with notes on installation/build/execution of systems and code we provided

### Operating System

See [Fedora IoT](fedora-iot.md) to see how we made the edge device work, and [aarch64 Virtual Machine](aarch64-vm.md) for the container build.

### Sensors Service

#### Python Application

See [QIoT Sensor](qiot-sensor.md) for details.

Application code is here: [qiot-sensor-py](https://github.com/QIoT-fr-FR-utf8/qiot-sensor-py)

Container images are here: [qiot-sensor](https://quay.io/repository/acb-fr/qiot-sensor)

#### Metrics

See [Device Metrics](prometheus.md) for details.

Container code is here: [qiot-prometheus](https://github.com/QIoT-fr-FR-utf8/qiot-sensor-service-base/tree/master/prom)

Container images are here: [qiot-sensor-prom](https://quay.io/repository/acb-fr/qiot-sensor-prom)

### Edge Service

See [Edge Service](edge-service.md) for details.

Application code is here: [qiot-edge-service](https://github.com/QIoT-fr-FR-utf8/qiot-edge-service)

Container images are here: [qiot-egde-service](https://quay.io/repository/acb-fr/qiot-edge-service)

## Hackfest feedback

See [feedback](feedback.md) for some team and personal remarks on this event.

<!-- ## SlideShow

See [slides](slideshow.html) used for the end of project presentation. -->
