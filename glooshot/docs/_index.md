---
title: Gloo Shot
weight: 99
---

#### Service Mesh Chaos Engineering

Gloo Shot is a chaos engineering framework for service meshes.


## Using Gloo Shot
- **Harden your applications**: Gloo Shot allows you to test failure modes before they occur in production.
- **Preview architectural changes**: Real deployments have different performance characteristics than your production environment. Gloo Shot allows you to simulate your productionn environment (latency, faults, etc.) prior to deployment.

### Getting started

- Gloo Shot is easy to [install](/installation) from the `glooshot` command line tool.
  - Once Gloo Shot is installed, you can trigger experiments with familiar `kubectl` commands.
  - Please see our [getting started tutorial](/tutorial) for a quick start usage overview.

### Experiment specification

- Gloo Shot has an expressive API for designing targeted experiments in your service mesh.
- You can specify [fault injections](/v1/github.com/solo-io/supergloo/api/v1/routing.proto.sk/#faultinjection) in the form of:
  - [Response delays](/v1/github.com/solo-io/supergloo/api/v1/routing.proto.sk/#delay) - simulate network delays
  - [Aborted responses](/v1/github.com/solo-io/supergloo/api/v1/routing.proto.sk/#abort) - simulate outages
- These faults can be applied to any [upstream](https://gloo.solo.io/v1/github.com/solo-io/gloo/projects/gloo/api/v1/upstream.proto.sk/#Upstream) for all requests or for a specified precentage of the requests.
  - In an upcoming release, Gloo Shot will support even more [target selectors](https://supergloo.solo.io/v1/github.com/solo-io/supergloo/api/v1/selector.proto.sk/)
- Experiments automatically terminate according to your specification.
  - Failure condition - [Prometheus](https://prometheus.io/) metric value threshold or a custom webhook
  - Timeout - if none of the metric thresholds are exceeded, Gloo Shot will terminate the experiment after a set duration.


## What makes Gloo Shot unique
- **Integration with service meshes**: Gloo Shot was designed for service mesh environments. It leverages [Supergloo](https://supergloo.solo.io/) for a consistent interface to multiple different service meshes.
- **Kubernetes-native experiment specifications**: Gloo Shot's configuration resources are specified in Custom Resource Definitions (CRDs) which means that you can manage experiments with familiar `kubectl` commands.


### Next Steps
- Join us on our slack channel: [https://slack.solo.io/](https://slack.solo.io/)
- Follow us on Twitter: [https://twitter.com/soloio_inc](https://twitter.com/soloio_inc)
- Check out the docs: [https://gloo.solo.io](https://gloo.solo.io)
- Check out the code and contribute: [Contribution Guide](CONTRIBUTING.md)
- Contribute to the [Docs](https://github.com/solo-io/solo-docs)

### Thanks

**Gloo Shot** would not be possible without the valuable open-source work of projects in the community. We would like to extend a special thank-you to [Envoy](https://www.envoyproxy.io).
