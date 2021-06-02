# Architecture Patterns

> #### sources :
>[Fundamentals of Software Architecture](https://www.oreilly.com/library/view/fundamentals-of-software/9781492043447/)

_The following are the most used/common architecture patterns :_
![](./images/patterns.png)

## 1. Layered pattern

This pattern can be used to structure programs that can be decomposed into groups of subtasks, each of which is at a
particular level of abstraction. Each layer provides services to the next higher layer. The most commonly found 4 layers
of a general information system are as follows -

* Presentation layer (also known as UI layer)
* Application layer (also known as service layer)
* Business logic layer (also known as domain layer)
* Data access layer (also known as persistence layer)

<img src="https://www.oreilly.com/library/view/software-architecture-patterns/9781491971437/assets/sapr_0104.png" height="400" width="500">

#### USAGE

* Desktop Applications
* E-commerce web applications etc.

## 2. Modular Monolith

Monolith is a system that has exactly one deployment unit. Modular Monolith architecture is an explicit name for a
Monolith system designed in a modular way. To achieve a high level of modularization each module must be independent,
has everything necessary to provide desired functionality (separation by business area), encapsulated and have a
well-defined interface/contract. The Modular Monolith architecture breaks up the code into independent modules for each
of the features needed in your application. Each module only link to other modules that specifically provides services
it needs.

<img src="https://miro.medium.com/max/1484/1*nyy-y-ZqOyzybXB4qTxtUQ.jpeg" height="400" width="600">

## 3. Micro-kernel

The microkernel architecture pattern (sometimes referred to as the plug-in architecture pattern) is a natural pattern
for implementing product-based applications. A product-based application is one that is packaged and made available for
download in versions as a typical third-party product. However, many companies also develop and release their internal
business applications like software products, complete with versions, release notes, and pluggable features. These are
also a natural fit for this pattern. The microkernel architecture pattern allows you to add additional application
features as plug-ins to the core application, providing extensibility as well as feature separation and isolation.

<img src="https://www.oreilly.com/library/view/software-architecture-patterns/9781491971437/assets/sapr_0301.png" height="400" width="600">

The plug-in modules are stand-alone, independent components that contain specialized processing, additional features,
and custom code that is meant to enhance or extend the core system to produce additional business capabilities.
Generally, plug-in modules should be independent of other plug-in modules, but you can certainly design plug-ins that
require other plug-ins to be present. Either way, it is important to keep the communication between plug-ins to a
minimum to avoid dependency issues.

The core system needs to know about which plug-in modules are available and how to get to them. One common way of
implementing this is through some sort of plug-in registry. This registry contains information about each plug-in
module, including things like its name, data contract, and remote access protocol details (depending on how the plug-in
is connected to the core system).

Plug-in modules can be connected to the core system through a variety of ways, including OSGi (open service gateway
initiative), messaging, web services, or even direct point-to-point binding (i.e., object instantiation).

#### USAGE

* Eclipse
* Product based software
* Insurance softwares

## 3. Micro-services

Microservice architecture – a variant of the service-oriented architecture (SOA) structural style – arranges an
application as a collection of loosely coupled services. In a microservices architecture, services are fine-grained and
the protocols are lightweight.

<img src="https://microservices.io/i/Microservice_Architecture.png">

#### Benefits

The benefit of decomposing an application into different smaller services are numerous:

* **Modularity:** This makes the application easier to understand, develop, test, and become more resilient to
  architecture erosion.This benefit is often argued in comparison to the complexity of monolithic architectures
* **Scalability:** Since microservices are implemented and deployed independently of each other, i.e. they run within
  independent processes, they can be monitored and scaled independently.
* **Integration of heterogeneous and legacy systems:** microservices is considered as a viable means for modernizing
  existing monolithic software application. There are experience reports of several companies who have successfully
  replaced (parts of) their existing software by microservices, or are in the process of doing so. The process for
  Software modernization of legacy applications is done using an incremental approach.
* **Distributed development:** it parallelizes development by enabling small autonomous teams to develop, deploy and
  scale their respective services independently. It also allows the architecture of an individual service to emerge
  through continuous refactoring. Microservice-based architectures facilitate continuous integration, continuous
  delivery and deployment.

## 4. Service based Architecture

Service-based architectures consist of tens of deployable services, rather than the hundreds or thousands advocated by
microservice proponents. These services may have separate datastores, or may still share a single monolithic datastore.

<img src="https://res.infoq.com/news/2016/10/service-based-architecture/en/resources/figure1.jpg" height="400" width="600">

Service-based architectures limit the number of network calls by grouping much larger chunks of code together by domain.
This should result in better performance. What might have been a call graph of a dozen related microservices becomes
method calls within a single service.

A service-based architecture provides more delivery speed than a monolith or service-oriented architecture (SOA) by
breaking the code apart in the domain-centric way advocated by microservice and DDD proponents