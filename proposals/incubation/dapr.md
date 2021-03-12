# Distributed Application Runtime CNCF Proposal

## Name of project

Distributed Application Runtime (Dapr)

## Project description

Distributed Application Runtime (Dapr) is portable, event-driven runtime that makes it easy for developers to build resilient, microservice stateless and stateful applications that run on the cloud and edge. 

## Overview

Using Dapr you can easily build microservice applications using any language, any framework, and run them anywhere.

Today developers are comfortable with web + database application architectures but not with microservice application architectures which are inherently distributed. It’s hard to become a distributed systems expert, nor should they have to. Developers want to focus on business logic, while leaning on the platforms to imbue their applications with scale, resiliency, maintainability, elasticity and the other attributes of cloud-native architectures.

Dapr codifies the best practices for building microservice applications into open, independent, building blocks exposed via a consistent API that enable you to build portable applications with the language and framework of your choice. Each building block is completely independent and you can use one, some, or all of them in your application.

Dapr is platform agnostic meaning you can run your applications locally, on any Kubernetes cluster, and other hosting environments. This enables you to build microservice applications that can run on the cloud and edge.

### About Dapr

Dapr exposes its APIs as a sidecar architecture, either as a container or as a process, not requiring the application code to include any Dapr runtime code. This makes integration with Dapr easy from other runtimes, as well as providing separation of the application logic.  

Dapr can be hosted in multiple environments, including self hosted for local development, to a group of VMs, Kubernetes and edge environments. Dapr is has a control plane that is deployed and integrated with the hosting environment, with Kubernetes currently being the preferred choice for production.  

Dapr released as a v1.0 project in Feb 2021 and has achieved the stability and enterprise readiness to be designated production ready. Dapr is used in production today by customers. 

### Features

Dapr consists of a high-performance runtime, CLI, language specific SDKs (Java, Python, Go, .NET, PHP, C++, Javascript) and pluggable components for a range of different technologies including storage, queue, event brokers etc.

Dapr has a set of [building block APIs](https://docs.dapr.io/concepts/building-blocks-concept/) that can use pluggable [components](https://docs.dapr.io/concepts/components-concept/) to provide a developer abstraction, code portability and hosting independence.

| Building Block | Description |
|----------------|-------------|
| Service-to-service invocation | Resilient service-to-service invocation enables method calls, including retries, on remote services wherever they are located in the hosting environment.
| State management| State management for storing key/value pairs, enables long running, highly available, stateful services.
| Publish and subscribe | Publishing events and subscribing to topics using Cloud Events, enables scalable, event-driven services.
| Resource bindings | Resource bindings with triggers builds further on event-driven architectures by receiving and sending events to and from any external source such as databases, queues, file systems, etc.
| Actors | A pattern for stateful and stateless objects that make concurrency simple with method and state encapsulation. 
| Observability | Dapr emit metrics, logs, and traces to debug and monitor both Dapr and user applications. Distributed tracing uses  W3C Trace Context and Open Telemetry and supports all monitoring tools including Prometheus, Fluent and Grafana. 
| Secrets | Secrets management integrates with public cloud and local secret stores to retrieve the secrets for use in application code.

The Dapr CLI provides for a simple local development experience to develop, build and test cloud native applications. 

Although Dapr dan be used with simple HTTP or gRPC localhost calls, language SDKs provide a more familar developer experience and integration with language specific tooling.

## Statement on alignment with CNCF charter mission

Dapr is aligned with the CNCF mission to make cloud native computing ubiquitous for developers. Dapr enables developers to build scalable, cloud native applications faster and also make them portable across different clouds, bringing true multi-cloud experience to application. Dapr is community-led project that has an open governance charter with a large and rapidly growing community, which is why we are donating it to the CNCF.

## Comparison with similar projects (inside or outside the CNCF), including what differentiates this project

Dapr is a developer focused technology and so there is less to compare with in CNCF today. 

[Micro](https://github.com/micro/micro) is a microservices framework that has some similaries to Dapr. A significant differnce is that Dapr is a set of APIs that can be used from any language or framework and is incremental in its usage. Most framework like Micro are restricted to certain languages and do not expose a common API that can be extended by the community

- Service meshes such as CNCF **[Linkerd](https://github.com/linkerd/linkerd)** and non-CNCF **[Istio](https://github.com/istio/istio)** both have network routing, security and observability that Dapr also provides. The primary difference between Dapr and service meshes, is that Dapr operates at the layer 7 application level for developers, whereas service meshes operate at the infrastructure networking layer 4 level.

- Dapr uses many CNCF projects that are developer focused including;
- [CloudEvents](https://github.com/cloudevents/spec) for all publish/subscribe events.
- [gRPC](https://github.com/grpc) for high-performance remote procedure calls (RPC).
- [SPIFFE](https://github.com/spiffe/spiffe) for identifying and securing communications between application services.
- [Open Telemetry](https://github.com/open-telemetry) to generate, collect, and export telemetry data.
- [Helm](https://github.com/helm/helm) used to deploy Dapr control plane to Kubernetes.

Dapr also integrates with several CNCF projects including;
- [Prometheus](https://github.com/prometheus) to collect and analyse metrics 
- [Jaeger](https://github.com/jaegertracing/jaeger) for distributed tracing
- [NATS](https://github.com/nats-io) as a high performance open source messaging system for cloud native applications
- [KEDA](https://github.com/kedacore/keda)for fine-grained autoscaling on Kubernetes

## Sponsor from TOC

Lei Zhang (Harry)

## Preferred maturity level

Incubation

## License

Currently MIT (https://github.com/dapr/dapr/blob/master/LICENSE) - happy to relicense to Apache2 at donation.

## Source control
Dapr is a GitHub organization with several repos 

GitHub: https://github.com/dapr

## External dependencies (including licenses)

Currently Dapr uses go 1.15 with the following dependencies:

**TODO** - Yaron add
        
## Initial committers (how long working on project, companies they represent)

Initial committers were from Microsoft.
* Yaron Schneider (@yaron2, Microsoft)
* Haishi Bai (@Haishi2016, Microsoft)
* Mark Fussell (@msfussell, Microsoft) 

This link https://github.com/orgs/dapr/teams captures the list of Daprs current maintainers and approvers.

Dapr is completely developed in the open with transparent community ownership, governance, and contributions. Microsoft has the major of maintainers currently, however there are maintainers and approvers from the community for serveral Dapr repos and we are actively adding more. Each repo has a code owners file, for example https://github.com/dapr/dapr/blob/master/CODEOWNERS

## Infrastructure requests (CI / CNCF Cluster)

No infrastructure requests at this time.

## Communication channels (slack, irc, mailing lists)
See the [Dapr community repo](https://github.com/dapr/community) specifically [communication ](https://github.com/dapr/community#communication)

[Dapr Discord](https://discord.com/invite/ptHhX6jc34) is the primary community engagement and Q&A. There is a twice-monthly community call for open Q&A, news, demos and roadmap.

## Issue tracker
Issues are tracked in each of the Dapr repos https://github.com/dapr

See https://github.com/dapr/dapr/issues

## Website

- Website https://dapr.io/
- Documentation https://docs.dapr.io/ 

## Release methodology and mechanics

Dapr reached [v1.0 maturity in Feb 2021](https://blog.dapr.io/posts/2021/02/17/announcing-dapr-v1.0/) having worked closely with customers such as Zeiss, Ignition Group and Morgan Stanley as well as partners such as Alibaba. 

### Milestone release plan
Each milestone release plan is tracked with an issue, for example these are the plans from the v1.0 and v1.1 releases.
- [Milestone release plan v1.0](https://github.com/dapr/dapr/issues/2346)
- [Milestone release plan v1.1](https://github.com/dapr/dapr/issues/2843) 

Each release sets dates and brings together milestones from the maintainers of each of the Dapr repos. Current and next milestones for each repo are maintained. See https://github.com/dapr/dapr/milestones

### Milestone release endgame plan
Each release endgame plan is tracked with an issue for example this is the release endgame plan for v1.0.

 - [Milestone release endgame v1.0](https://github.com/dapr/dapr/issues/2724)

The endgame tracking the steps to cut a supported release, which can go through a number of release candidates (RCs) during the endgame phase. The RCs are opportunities for customers in production and community members to raise any issues that they encounter.

Dapr has a versioning policy for releases which is described in the [Versioning policy](https://docs.dapr.io/operations/support/support-versioning/) documentation.

Dapr has a rolling window of supported releases. Dapr's supported release policy is described in the [Supported releases](https://docs.dapr.io/operations/support/support-release-policy/) documentation. 

## Social media accounts

Twitter: @daprdev

## Community size and any existing sponsorship

Currently 736 committers over the last 16 months, which has grown rapidly over the last year. For example committers include people from Alibaba, Disney, Morgan Stanley, Citigroup and Hashicorp. 

As for sponsorship, Microsoft currently pays for the project’s GitHub, infrastructure for testing, Website hosting and Docker repos.

## Who is currently known to be using the project? Are they using it in production and at what scale? (It may be hard to obtain accurate data for this, but any supporting evidence of usage is helpful)

Dapr has customers running in production with the v1.0 release. Publicly announced ones include; 

- [ZEISS](https://customers.microsoft.com/en-us/story/1336089737047375040-zeiss-accelerates-cloud-first-development-on-azure-and-streamlines-order-processing), an international technology leader in optics and opto-electronics. Scale is the process of multi-region rollout.
- [Ignition Group](https://customers.microsoft.com/en-us/story/1335733425802443016-ignition-group-speeds-development-and-payment-processing-using-dapr-and-azure) a South Africa–based technology business focusing on customer engagement that builds sales-support tools and value-added services for telcos. Scale is the process of multi-region rollout.
- [Roadwork](https://blog.dapr.io/posts/2021/02/09/running-dapr-in-production-at-roadwork/) a company the enables customers to gain actionable insights from their data

Others customers can be provided who can talk about their projects under a non-disclosure agreement that we have worked with over the last year.

Dapr is used by Alibaba cloud where Dapr is used in the serverless infrastructure and they have contributed back to the project. 

## Project logo in svg format

All logos are available in https://github.com/dapr/docs/tree/v1.0/daprdocs/assets/icons

The svg main logo is here: https://github.com/dapr/docs/blob/v1.0/daprdocs/assets/icons/logo.png 
