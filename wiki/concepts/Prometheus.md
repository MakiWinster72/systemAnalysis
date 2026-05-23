---
sources: [summaries/20.3.5运维监控.md]
brief: Prometheus是一款开源的监控告警工具，采用pull模式采集指标数据，由SoundCloud公司开发，包含四大核心组件。
---

# Prometheus监控与告警工具

## 概述

Prometheus是一款开源的监控和告警工具，最初由SoundCloud公司开发。它采用基于**pull**的方式从被监控的应用中获取指标数据，并通过一系列规则进行聚合、存储和展示。Prometheus支持多种数据模型，如时间序列数据模型、标签数据模型等，使得用户可以更加方便地对不同种类的数据进行管理和处理。

## 核心组件

Prometheus包含四个核心组件：

### Prometheus Server

Prometheus Server是Prometheus的核心组件，负责从各种数据源（如应用、主机、数据库等）中拉取指标数据，并将其存储到本地的时间序列数据库中。同时，Prometheus Server还提供了一个HTTP API，允许用户查询和聚合数据，并通过内置的表达式语言**PromQL**对数据进行过滤和计算。

### Client Library

Client Library是一组用于收集指标数据的库，支持多种编程语言，如Go、Java、Python等。它提供了丰富的API，允许开发者在应用程序中埋点，从而收集各种指标数据，如计数器（Counter）、直方图（Histogram）、摘要（Summary）等。

### Push Gateway

Push Gateway是Prometheus的一个可选组件，它允许应用程序主动将指标数据推送到Prometheus Server，而不是等待Server拉取。Push Gateway适用于一些短周期的任务，如批处理作业等场景。

### Alertmanager

Alertmanager是Prometheus的告警管理器，负责接收Prometheus Server发送的告警通知，并根据一些预定义的规则进行分组和筛选，最终将告警发送给指定的接收者，如邮件、短信、Slack等渠道。

## 技术特点

- **Pull模式采集**：Prometheus采用主动拉取的方式从目标应用获取指标数据
- **时间序列存储**：内置时间序列数据库存储指标数据
- **多数据模型支持**：支持时间序列数据和标签数据模型
- **强大的查询能力**：通过PromQL表达式语言实现灵活的数据查询和聚合
- **可扩展生态**：提供Grafana、PushProx等插件和工具，支持灵活扩展

## 应用场景

Prometheus广泛应用于微服务架构的监控场景，可用于：

- 监控服务的响应时间和吞吐量
- 追踪CPU和内存使用情况
- 分析网络流量指标
- 配置告警规则实现主动发现问题

## 相关工具

Prometheus常与[[Grafana数据可视化平台]]配合使用，通过Grafana实现监控数据的可视化展示。两者结合构成了现代云原生监控体系的重要组成部分。

> 参考文档：[[summaries/20.3.5运维监控]]