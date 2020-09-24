# Quarkus for IoT Hackfest

## Introduction

The QIoT project is designed for EMEA App Dev partners interested in new Red Hat Cloud-Native Technologies and Edge Architecture design and implementation

EMEA App Dev Partners join the project participating in a Hackfest, a challenge for Partners to implement a real-world use-case scenario.

[Axians Cloud Builder](https://www.axians.fr), as a French Red Hat Partner, participates to this hackfest.

This challenge was done in September 2020, in France, Earth, during our free time (almost).

You will find below some documentation about that challenge.

Happy hacking!

## Team

We are the "Axians Cloud Builder" France team, with:

* David Auffray
* Sébastien Davoult
* Jérémy Hoarau
* Chamseddine Saadoune
* Rémi Verchère

See [team organization](organization.md) to see how we worked on the project.

You will find some team and personal [feedback](feedback.md) on this event.

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

See [QIoT Sensor](qiot-sensor.md)

#### Metrics

See [Device Metrics](prometheus.md)

### Edge Service

See [Edge Service](edge-service.md)

