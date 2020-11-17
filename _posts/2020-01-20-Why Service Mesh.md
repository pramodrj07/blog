---
layout: post
title:  "Why would we need a service mesh?"
author: pramod
categories: [ servicemesh, kubernetes ]
image: assets/images/servicemesh.jpg
tags: featured
---
Service Mesh is typically an infrastructure layer to secure, manage and connect your Microservices. 

Well.. Well.. Why would we even need an infra layer on top of an awesome infra layer? Like k8s..

Though kubernetes offers excellent way to deploy, manage and scale you applications and microservices, it still needs to be secured. Though one can imagine the security to be handled at the API gateway and external load balancer level, the need arises when the communication takes places between the microservices inside the cluster. 

How would a traffic be fine grained to a specific pod of a microservice for your sticky session?
How would the mTLS be established between the micorservices running within your cluster?
Is it possible to introduce your testing code to your existing running prod instances without an outage?

All the above questions and more can be solved using a Servicemesh.

Kubernetes is aimed to ease the job of a application developer. Wouldn't a developer want to offload the Security, Traffic and network responsibility to someone else?