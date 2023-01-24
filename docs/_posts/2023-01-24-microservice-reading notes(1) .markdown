---
layout: post
title:  "Spring Microservice in action reading notes(1)"
date:   2023-01-24 08:46:12 -0600
categories: microservice
---
# microservice

basics of building microservice:

1. service granularity — the way to decompose a business domain into microservices  so that each microservice has the right level of responsibility
2. communication protocols — 
    1. synchronous, HTTP based REST
    2. asynchronous, AMQP(advanced message queuing protocol), one-to-one(queue), one-to-many(topic) with message broker such as RabbitMQ, Apache Kafka, and Amazon Simple Queue Service(SQS)
3. interface design — the way to expose service endpoints to client
4. configuration management — the way to manage the configuration of the microservice to move between different environment in the cloud
5. event processing between service — decouple the microservice using event in order to minimize hardcoded dependencies between the services and increase the resiliency of application

**service routing** — gives the microservice client a single logical URL to talk to and acts as a policy enforcement point for things like authorization, authentication, and content checking

**service discovery** — abstracts away the physical location of the service from the client

client resiliency

client load balancing — the way to cache the location of all health service instances on the service

circuit breaker pattern — the way to prevent the client from continuing to call a service that’s failing or suffering performance issues  

fallback pattern — when a service call fails, the mechanism provided to carry out its work through alternative way

bulkhead pattern — the way to compartmentalize the calls so that the misbehavior of one service call can’t negatively impact the rest of the application

> Heroku’s best practice guide — [twelve-factor app](https://12factor.net/)
> 
- codebase
- dependencies
- config
- backing services
- build, run, release
- processes
- port binding
- concurrency
- disposability
- dev/prod parity
- logs
- admin processes