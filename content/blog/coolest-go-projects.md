+++
draft = false
section = "blog"
title = "Coolest Open Source Go Projects in the Wild"
description = "Find out how is used in the wild"
pubdate = "2017-05-29T10:56:00+01:00"
date = "2017-05-29T10:56:00+01:00"
keywords = ["go"]
tags = ["go"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/coolest-open-source-go-projects-in-the-wild"
disqus_identifier = "coolest-open-source-go-projects-in-the-wild"
disqus_title = "Coolest Open Source Go Projects in the Wild"
has_code = false
+++

This post is based on a section of the [“Everything You Need to Know to Start with Go”](https://peteraba.com/post/everything-you-need-to-know-to-start-with-go) post. Since than I realised that this post will be my own personal version of [Awesome-Go](https://github.com/avelino/awesome-go), I will regularly update that post but as the Go communinity is booming, the interesting projects would just take over the rest of the material there, so I decided to create a separate post for cool, interesting projects being done in Go. Only projects which have an open source component will make this list.

## Frameworks and other tool kits

### Go kit - toolkit for microservices (MIT, pre-stable, 0.4.0)
 - [Website](https://gokit.io/)
 - [Source code](https://github.com/go-kit/kit)
 - [Releases](https://github.com/go-kit/kit/releases)
 - [A Standard Library for Distributed Programming (video)](https://github.com/go-kit/kit)
 - [A Toolkit for Microservices (video)](https://www.youtube.com/watch?v=aL6sd4d4hxk)

### Echo - High performance, extensible, minimalist Go web framework (MIT, stable, v3.1.0)
 - [Website](https://echo.labstack.com/)
 - [Documentation](https://echo.labstack.com/guide)
 - [Source code](https://github.com/labstack/echo)
 - [Releases](https://github.com/labstack/echo/releases)

## Containers

### Docker Moby - container ecosystem
 - [Website](https://mobyproject.org/)
 - [Documentation](https://docs.docker.com/)
 - [Source code](https://github.com/moby/moby)
 - [Releases](https://github.com/moby/moby/releases)

### Kubernetes - Container Scheduling and Management (Apache-2.0, stable, v1.6.4)
 - [Website](https://kubernetes.io/)
 - [Source code](https://github.com/kubernetes/kubernetes)
 - [Releases](https://github.com/kubernetes/kubernetes/releases)
 - [Documentation](https://kubernetes.io/docs/home/)

### Consul - Service Discovery and Configuration (MPL-2.0, pre-stable, v0.8.3)
 - [Website](https://www.consul.io/)
 - [Documentation](https://www.consul.io/docs/index.html)
 - [Source code](https://github.com/hashicorp/consul)
 - [Releases](https://github.com/hashicorp/consul/releases)

### Terraform - (MPL-2.0, pre-stable, v0.9.6)
 - [Website](https://www.terraform.io/)
 - [Documentation](https://www.terraform.io/docs/index.html)
 - [Source code](https://github.com/hashicorp/terraform)
 - [Releases](https://github.com/hashicorp/terraform/releases)

### Nomad - Distributed, Highly Available, Datacenter-Aware Scheduler (MPL-2.0, pre-stable, v0.5.6)
 - [Website](https://www.nomadproject.io/)
 - [Documentation](https://www.nomadproject.io/docs/index.html)
 - [Source code](https://github.com/hashicorp/nomad)
 - [Releases](https://github.com/hashicorp/nomad/releases)

## Logging, alerting, metrics

### Prometheus - monitoring system and time series database (Apache-2.0, stable, 1.6.3)
 - [Website](https://prometheus.io/)
 - [Source code](https://github.com/prometheus/prometheus)
 - [Releases](https://github.com/prometheus/prometheus/releases)
 - [Designing and Implementing a Modern Monitoring Solution (video)](https://www.youtube.com/watch?v=1V7eJ0jN8-E)
 - [CloudNativeCon 2017 videos - Prometheus track here (video series](https://www.youtube.com/watch?v=uV_sh7_lVw8&list=PLqm7NmbgjUExeDZU8xb2nxz-ysnjuC2Mz&index=1)

### InfluxDB - scalable datastore for metrics, events, and real-time analytics (MIT, stable, v1.2.4)
 - [Website](https://www.influxdata.com/)
 - [Source code](https://github.com/influxdata/influxdb)
 - [Releases](https://github.com/influxdata/influxdb/releases)

### Grafana - beautiful monitoring and metric analytics & dashboards (Apache-2.0, stable, v4.3.1)
 - [Website](https://grafana.com/)
 - [Documentation](http://docs.grafana.org/)
 - [Source code](https://github.com/grafana/grafana)
 - [Releases](https://github.com/grafana/grafana/releases)

### OKLog - distributed and coördination-free log management system (Apache-2.0, pre-stable, v0.2.1)
 - [Blog post](https://peter.bourgon.org/ok-log/)
 - [Source code](https://github.com/oklog/oklog)
 - [Releases](https://github.com/oklog/oklog/releases)

### Telegraf - plugin-driven server agent for collecting & reporting metrics (MIT, stable, 1.3.0)
 - [Source code](https://github.com/influxdata/telegraf)
 - [Releases](https://github.com/influxdata/telegraf/release)

### Bosun - Time Series Alerting Framework (MIT, pre-stable, 0.5.0)
 - [Website](http://bosun.org/)
 - [Documentation](http://bosun.org/quickstart)
 - [Source code](https://github.com/bosun-monitor/bosun)
 - [Releases](https://github.com/bosun-monitor/bosun/releases)

### Zap - structured, leveled logging (MIT, stable, v1.4.0)
 - [Source code](https://github.com/uber-go/zap)
 - [Releases](https://github.com/uber-go/zap/releases)

## Servers

### Traefik - reverse proxy (MIT, stable, v1.2.3)
 - [Website](https://traefik.io/)
 - [Source code](https://github.com/containous/traefik)
 - [Releases](https://github.com/containous/traefik/releases)

### Caddy - Fast, cross-platform HTTP/2 web server with automatic HTTPS (Apache-2.0, pre-stable, 0.10.3)
 - [Website](https://caddyserver.com/)
 - [Source code](https://github.com/mholt/caddy)
 - [Releases](https://github.com/mholt/caddy/releases)

### Websocketd - Turn any program that uses STDIN/STDOUT into a WebSocket server (BSD-2-clause, pre-stable, v0.2.12)
 - [Website](http://websocketd.com/)
 - [Documentation](https://github.com/joewalnes/websocketd/wiki)
 - [Source code](https://github.com/joewalnes/websocketd)
 - [Releases](https://github.com/joewalnes/websocketd/releases)

## Other DevOps

### Functions as a Service (MIT, alpha, 0.5.5-alpha)
 - [Source code](https://github.com/alexellis/faas)
 - [Releases](https://github.com/alexellis/faas/releases)
 - [Documentation](http://docs.get-faas.com/)
 - [Deep Dive into Functions as a Service (FaaS) on Docker (video)](https://www.youtube.com/watch?v=sp1B7l5mEzc)
 - [Tour of FaaS framework (video)](https://www.youtube.com/watch?v=BK076ChLKKE)
 - [Dockercon 2017: Moby's Cool Hack Sessions](https://blog.docker.com/2017/04/dockercon-2017-mobys-cool-hack-sessions/)

### Apex - Build, deploy, and manage AWS Lambda functions (MIT, pre-stable, v0.14.0)
 - [Source code](https://github.com/apex/apex)
 - [Releases](https://github.com/apex/apex/releases)

### Flynn - Platform as a service (???, pre-stable)
 - [Website](https://flynn.io/)
 - [Documentation](https://flynn.io/docs/basics)
 - [Source code](https://github.com/flynn/flynn)
 - [Releases](https://github.com/flynn/flynn/releases)
 - [License](https://github.com/flynn/flynn/blob/master/LICENSE)

### syncthing - Continuous File Synchronization (MPL 2.0, pre-stable, v0.14.28)
 - [Source code](https://github.com/syncthing/syncthing)
 - [Releases](https://github.com/syncthing/syncthing/releases)

### Drone - Continuous Delivery platform built on Docker (Apache-2.0, pre-stable, v0.7.1)
 - [Source code](https://github.com/drone/drone)
 - [Releases](https://github.com/drone/drone/releases)

### Teleport - Modern SSH server for clusters and teams (Apache-2.0, stable, v2.0.6)
 - [Website](http://gravitational.com/teleport/)
 - [Documentation](http://gravitational.com/teleport/docs/2.0/quickstart/)
 - [Source code](https://github.com/gravitational/teleport)
 - [Releases](https://github.com/gravitational/teleport/releases)

### Minio - Minio is an open source object storage server compatible with Amazon S3 APIs  (Apache-2.0, pre-stable, ???)
 - [Website](https://minio.io/)
 - [Documentation](https://docs.minio.io/)
 - [Source code](https://github.com/minio/minio)
 - [Releases](https://github.com/minio/minio/releases)

## Testing

### k6 - Load Testing tool (AGPL-3.0, pre-stable, v0.15.0)
 - [Website](https://k6.io/)
 - [Source code](https://github.com/loadimpact/k6)
 - [Releases](https://github.com/loadimpact/k6/releases)
 - [Documentation](https://docs.k6.io/)

### wuzz - Interactive cli tool for HTTP inspection (AGPL-3.0, pre-stable, v0.3.0)
 - [Source code](https://github.com/asciimoo/wuzz)
 - [Releases](https://github.com/asciimoo/wuzz/releases)

## Databases

### CockroachDB - the scalable, survivable, strongly-consistent SQL database (custom, stable, v1.0.1)
 - [Source code](https://github.com/cockroachdb/cockroach)
 - [Releases](https://github.com/cockroachdb/cockroach/releases)
 - [License](https://github.com/cockroachdb/cockroach/blob/master/LICENSE)

### TiDB - distributed NewSQL database compatible with MySQL protocol (Apache-2.0, pre-stable, rc)
 - [Source code](https://github.com/pingcap/tidb)
 - [Releases](https://github.com/pingcap/tidb/releases)
 - [Documentation](https://github.com/pingcap/tidb)

### dgraph - graph database (AGPL-3.0, alpha, 0.7.7)
 - [Website](https://dgraph.io/)
 - [Source code](https://github.com/dgraph-io/dgraph)
 - [Releases](https://github.com/dgraph-io/dgraph/releases)
 - [Documentation](https://docs.dgraph.io/v0.7.7/get-started)

### tile38 - geospatial database (MIT, stable, 1.9.0)
 - [Website](http://tile38.com/)
 - [Source code](https://github.com/tidwall/tile38)
 - [Releases](https://github.com/tidwall/tile38/releases)
 - [Documentation](http://tile38.com/documentation/)

### etcd - key-value store (Apache-2.0, stable, v3.1.8)
 - [Source code](https://github.com/coreos/etcd)
 - [Releases](https://github.com/coreos/etcd/releases)

### cayley - graph database (Apache-2.0, pre-stable, v0.6.1)
 - [Source code](https://github.com/cayleygraph/cayley)
 - [Releases](https://github.com/cayleygraph/cayley/releases)

## Database tools

### Kallax - PostgreSQL typesafe ORM (MIT, stable, v1.2.5)
 - [Source code](https://github.com/src-d/go-kallax)
 - [Releases](https://github.com/src-d/go-kallax/releases)

## Frontend

### GopherJs - compiler from Go to JavaScript for running Go code in a browser (BSD-2-clause, pre-stable, none)
 - [Blog](https://medium.com/gopherjs)
 - [Playground](https://gopherjs.github.io/playground/)
 - [Source code](https://github.com/gopherjs/gopherjs)
 - [Releases](https://github.com/gopherjs/gopherjs/releases)

## CMSs and other project shortcuts

### Ponzu - CMS (BSD-3-clause, pre-stable, 0.9.2)
 - [Website](https://docs.ponzu-cms.org/)
 - [An Introduction (video)](https://www.youtube.com/watch?v=T_1ncPoLgrg)
 - [Source code](https://github.com/ponzu-cms/ponzu)
 - [Releases](https://github.com/ponzu-cms/ponzu/releases)

### Hugo - static website engine (Apache-2.0, pre-stable, v0.21)
 - [Website](https://gohugo.io/)
 - [Source code](https://github.com/spf13/hugo)
 - [Releases](https://github.com/spf13/hugo/releases)
 - [Documentation](http://gohugo.io/overview/introduction/)

## Source code

### Gogs - painless self-hosted Git service (MIT, pre-stable, 0.11.4)
 - [Website](https://gogs.io/)
 - [Documentation](https://gogs.io/docs)
 - [Source code](https://github.com/gogits/gogs)
 - [Releases](https://github.com/gogits/gogs/releases)

### Grumpy is a Python to Go source code transcompiler and runtime (Apache-2.0, pre-stable, ???)
 - [Source code](https://github.com/google/grumpy)
 - [Releases](https://github.com/google/grumpy/releases)

## Security

### Vault - A tool for managing secrets (MPL-2.0, pre-stable, v0.7.2)
 - [Website](https://www.vaultproject.io/)
 - [Documentation](https://www.vaultproject.io/docs/index.html)
 - [Source code](https://github.com/hashicorp/vault)
 - [Releases](https://github.com/hashicorp/vault/releases)

