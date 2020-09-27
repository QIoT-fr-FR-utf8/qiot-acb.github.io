# Feedback

* TOC
{:toc}

Here some feedback to Red Hat team, after spending some (fun) time on this project!

All the remarks are not in a specific order.

## Pros

### Technical

1. Challenge to use a full Red Hat solution

1. Challenge to work with arm64/aarch64 architecture, playing with cross-compilation

1. Pratice with containers, especially with podman + quay

    * Build images
    * Push / Pull to registries
    * Use CI/CD to automate the process

1. Play with Python and Flask, even if it was not the primary goal of that project

1. Discover Quarkus, and all its potential on edge side!

1. Finally find a real use case for our RPis @ home :)

### Non technical

1. Our team is distributed, and we never have time to work on a same project. This was an opportunity for us to take some time together

1. Opportunity to enforce our Red Hat partnership

1. Find some time on innovative projects

## Cons

### Technical

1. Guidelines maybe too restrictive (compared to the previous public hackfest)

1. Frustrated to not work on OpenShift platform

1. No way to have debug / logs information on the DataHub platform

### Non technical

1. The project was done during our free time, mostly (business first!). Then it was difficult work asynchronisly, by night, with all the team

1. We would like to have more collaboration between teams. We are 12 teams, but only few were tchating / help on the dedicated slack channel

## Our Vision, to Infinite and Beyond!

### Feedback and the following

1. (David) I think that the raspberry pi is not the best choice to do some IOT, the raspberry can be a gateway but not the main sensors retriever. For this example we could choose Arduino or other like ESP etc...

1. Our vision about this project it also add some metrics **ON** the edge (ex : via prometheus) in case of network failing, during this interruption we could always check in local

1. We need also more secure flow exchange between the edge device and the poller (now it is in Http)

1. We need also more security on the edge, the **OpenScap** can be one of this solution? or maybe a custom image or ...

1. To end, we build a quickly (in devel - not tested) ansible playbook which can be run either via Ansible Engine or Ansible AWX/Tower

### And Andrea, please, change your microphone ;)