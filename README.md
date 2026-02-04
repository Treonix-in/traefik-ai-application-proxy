
<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="docs/content/assets/img/traefik.logo-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="docs/content/assets/img/traefik.logo.png">
      <img alt="Traefik" title="Traefik" src="docs/content/assets/img/traefik.logo.png">
    </picture>
</p>

[![Docs](https://img.shields.io/badge/docs-current-brightgreen.svg)](https://doc.traefik.io/traefik)
[![Go Report Card](https://goreportcard.com/badge/traefik/traefik)](https://goreportcard.com/report/traefik/traefik)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/traefik/traefik/blob/master/LICENSE.md)
[![Join the community support forum at https://community.traefik.io/](https://img.shields.io/badge/style-register-green.svg?style=social&label=Discourse)](https://community.traefik.io/)
[![Twitter](https://img.shields.io/twitter/follow/traefik.svg?style=social)](https://twitter.com/intent/follow?screen_name=traefik)

Traefik (pronounced _traffic_) is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy.
Traefik integrates with your existing infrastructure components ([Docker](https://www.docker.com/), [Swarm mode](https://docs.docker.com/engine/swarm/), [Kubernetes](https://kubernetes.io), [Consul](https://www.consul.io/), [Etcd](https://coreos.com/etcd/), [Rancher v2](https://rancher.com), [Amazon ECS](https://aws.amazon.com/ecs), ...) and configures itself automatically and dynamically.
Pointing Traefik at your orchestrator should be the _only_ configuration step you need.

---

. **[Overview](#overview)** .
**[Features](#features)** .
**[Supported backends](#supported-backends)** .
**[Quickstart](#quickstart)** .
**[Web UI](#web-ui)** .
**[Documentation](#documentation)** .

. **[Support](#support)** .
**[Release cycle](#release-cycle)** .
**[Contributing](#contributing)** .
**[Maintainers](#maintainers)** .
**[Credits](#credits)** .

---

:warning: When migrating to a new major version of Traefik, please refer to the [migration guide](https://doc.traefik.io/traefik/migrate/v2-to-v3/) to ensure a smooth transition and to be aware of any breaking changes.


## Overview

Imagine that you have deployed a bunch of microservices with the help of an orchestrator (like Swarm or Kubernetes) or a service registry (like etcd or consul).
Now you want users to access these microservices, and you need a reverse proxy.

Traditional reverse-proxies require that you configure _each_ route that will connect paths and subdomains to _each_ microservice. 
In an environment where you add, remove, kill, upgrade, or scale your services _many_ times a day, the task of keeping the routes up to date becomes tedious. 

**This is when Traefik can help you!**

Traefik listens to your service registry/orchestrator API and instantly generates the routes so your microservices are connected to the outside world -- without further intervention from your part. 

**Run Traefik and let it do the work for you!** 
_(But if you'd rather configure some of your routes manually, Traefik supports that too!)_

![Architecture](docs/content/assets/img/traefik-architecture.png)

## Features

- Continuously updates its configuration (No restarts!)
- Supports multiple load balancing algorithms
- Provides HTTPS to your microservices by leveraging [Let's Encrypt](https://letsencrypt.org) (wildcard certificates support)
- Circuit breakers, retry
- See the magic through its clean web UI
- WebSocket, HTTP/2, gRPC ready
- Provides metrics (Rest, Prometheus, Datadog, Statsd, InfluxDB 2.X)
- Keeps access logs (JSON, CLF)
- Fast
- Exposes a Rest API
- Packaged as a single binary file (made with :heart: with go) and available as an [official](https://hub.docker.com/r/_/traefik/) docker image

## Supported Backends

- [Docker](https://doc.traefik.io/traefik/providers/docker/) / [Swarm mode](https://doc.traefik.io/traefik/providers/docker/)
- [Kubernetes](https://doc.traefik.io/traefik/providers/kubernetes-crd/)
- [ECS](https://doc.traefik.io/traefik/providers/ecs/)
- [File](https://doc.traefik.io/traefik/providers/file/)

## Quickstart

To get your hands on Traefik, you can use the [5-Minute Quickstart](https://doc.traefik.io/traefik/getting-started/quick-start/) in our documentation (you will need Docker).

## Web UI

You can access the simple HTML frontend of Traefik.

![Web UI Providers](docs/content/assets/img/webui-dashboard.png)

## Documentation

You can find the complete documentation of Traefik v3 at [https://doc.traefik.io/traefik/](https://doc.traefik.io/traefik/).

## Support

To get community support, you can:

- join the Traefik community forum: [![Join the chat at https://community.traefik.io/](https://img.shields.io/badge/style-register-green.svg?style=social&label=Discourse)](https://community.traefik.io/)

If you need commercial support, please contact [Traefik.io](https://traefik.io) by mail: <mailto:support@traefik.io>.

## Download

- Grab the latest binary from the [releases](https://github.com/traefik/traefik/releases) page and run it with the [sample configuration file](https://raw.githubusercontent.com/traefik/traefik/master/traefik.sample.toml):

```shell
./traefik --configFile=traefik.toml
```

- Or use the official tiny Docker image and run it with the [sample configuration file](https://raw.githubusercontent.com/traefik/traefik/master/traefik.sample.toml):

```shell
docker run -d -p 8080:8080 -p 80:80 -v $PWD/traefik.toml:/etc/traefik/traefik.toml traefik
```

- Or get the sources:

```shell
git clone https://github.com/Treonix-in/traefik-ai-application-proxy.git
```

