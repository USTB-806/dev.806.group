---
title: "开发运维"
date: 2025-11-13
draft: false
---
![beautiful_pic](/images/devops.jpg)
运行维护是开发者在部署、维护和扩展应用程序时需要掌握的知识和工具。

## Docker

Docker 是一个开源的容器化平台，用于开发、交付和运行应用程序。通过容器化，你可以将应用程序及其依赖打包成一个轻量级的、可移植的容器，确保在任何环境中一致运行。

Docker 的核心概念包括镜像（Image）、容器（Container）、Dockerfile 和 Docker Compose。镜像是一个只读模板，用于创建容器；容器是镜像的运行实例。

- Docker 核心概念
  - 镜像 (Image)
  - 容器 (Container)
  - Dockerfile
  - Docker Compose
- 容器管理
  - 容器生命周期（启动、停止、删除）
  - 网络和卷 (Volumes) 配置
  - 镜像推送和拉取

[访问官网](https://www.docker.com/) 了解更多。欲了解更多关于 Docker 的内容，请自行探索。



## CI/CD

持续集成（CI）和持续交付/部署（CD）是现代软件开发中的关键实践。CI/CD 自动化了代码集成、测试和部署过程，帮助团队更快、更可靠地交付软件。

常见的 CI/CD 工具包括 GitHub Actions、Jenkins、GitLab CI/CD 等。这些工具允许你定义流水线（Pipelines），自动运行测试、构建和部署。

- CI/CD 基本概念
  - 持续集成 (CI)
  - 持续交付/部署 (CD)
  - 流水线 (Pipelines)
- 流水线配置
  - 多阶段流水线（构建、测试、部署）
  - 环境变量和秘密管理
  - 失败处理和回滚
- 高级部署策略
  - 蓝绿部署
  - 金丝雀部署
  - 自动化监控集成

[访问 GitHub Actions 文档](https://docs.github.com/en/actions) 了解更多。欲了解更多关于 CI/CD 的内容，请自行探索。



## GitHub Pages 部署

GitHub Pages 是 GitHub 提供的免费静态网站托管服务，非常适合部署个人博客、项目文档、作品集等静态网站。结合 GitHub Actions，你可以实现自动化构建和部署工作流。

GitHub Pages 支持直接从仓库部署静态文件，也支持 Jekyll 等静态站点生成器。你可以使用自定义域名，并且 GitHub 会自动提供 HTTPS 支持。通过 GitHub Actions 工作流，每次推送代码时可以自动构建并部署网站。

- GitHub Pages 基础
  - 仓库分支部署
  - 自定义域名配置
  - HTTPS 自动支持
- 自动化部署
  - GitHub Actions 工作流
  - 构建流程配置
  - 缓存和优化
- 高级功能
  - 多环境部署
  - 回滚和故障处理
  - 性能优化和 SEO

[访问 GitHub Pages 文档](https://docs.github.com/en/pages) 了解更多。



## Linux

Linux 是一个开源的操作系统内核，许多服务器和嵌入式系统都基于它。掌握 Linux 是运行维护的基础，因为大多数生产环境运行在 Linux 上。

Linux 提供了强大的命令行工具、文件系统管理和进程控制。常见的发行版包括 Ubuntu、CentOS、Debian 等。

- 文件系统导航
  - 基本命令（ls、cd、pwd）
  - 文件管理（cp、mv、rm、mkdir）
  - 系统信息查看（uname、df、free）
- 用户和权限管理
  - 用户管理（useradd、usermod）
  - 权限控制（chmod、chown）
  - 软件包管理（apt、yum、dnf）
- 系统监控和维护
  - 进程管理（top、ps、kill）
  - 网络配置和防火墙
  - 日志管理和备份

欲了解更多关于 Linux 的内容，请自行探索。



## Shell 脚本

Shell 脚本是自动化运维任务的核心技能。通过编写 Shell 脚本，你可以自动化重复性任务，如系统监控、日志分析、备份等。

常用的 Shell 包括 Bash、Zsh 等。Shell 脚本支持变量、条件判断、循环、函数等编程特性，可以调用系统命令完成复杂的运维操作。

- 脚本基础
  - 变量和字符串操作
  - 条件判断（if-else）
  - 循环（for、while）
- 脚本编写
  - 函数定义
  - 命令行参数处理
  - 错误处理和调试
- 高级应用
  - 文本处理工具（grep、awk、sed）
  - 管道和重定向
  - 脚本库和模块化



## Systemd

Systemd 是现代 Linux 发行版的系统和服务管理器，用于启动、停止和管理系统服务。它提供了并行启动、按需激活和依赖管理等特性。

通过 Systemd，你可以创建自定义服务单元（Service Units），管理服务的生命周期，设置自动重启策略，以及查看服务日志。

- 服务管理
  - systemctl 命令使用
  - 服务日志查看（journalctl）
  - 开机自启配置
- 服务单元配置
  - 基本配置（Type、ExecStart、Restart）
  - 依赖关系（After、Requires）
  - 环境变量和工作目录
- 高级功能
  - 不同服务类型
  - 定时器（Timers）使用
  - 复杂服务配置



## Caddy/Nginx

Caddy 和 Nginx 是流行的 Web 服务器和反向代理服务器，用于处理 HTTP 请求、负载均衡和 SSL 证书管理。

Nginx 以高性能和稳定性著称，而 Caddy 以自动 HTTPS 和简单配置闻名。它们常用于部署 Web 应用程序、API 和静态站点。

- 基础配置
  - 安装和启动
  - 静态站点服务
  - 反向代理设置
- 安全和性能
  - SSL 证书配置
  - 负载均衡
  - 缓存和压缩
- 高级功能
  - WebSocket 支持
  - 限流和监控
  - 错误页面处理

[访问 Nginx 官网](https://nginx.org/) 和 [Caddy 官网](https://caddyserver.com/) 了解更多。欲了解更多关于反向代理的内容，请自行探索。



## Kubernetes

Kubernetes（简称 K8s）是一个开源的容器编排平台，用于自动化部署、扩展和管理容器化应用程序。它提供了强大的功能，如服务发现、负载均衡、自动扩展和自我修复。

Kubernetes 使用 Pod、Service、Deployment 等概念来管理容器。常见的工具包括 kubectl 命令行工具和 Helm 包管理器。

- 基础概念
  - Pod、Node 和 Cluster
  - kubectl 安装和使用
  - 简单应用部署
- 服务和配置
  - Service 和 Ingress
  - ConfigMap 和 Secret
  - Pod 状态监控
- 高级管理
  - Helm 包管理
  - 自动扩展（HPA）
  - 故障排查

[访问官网](https://kubernetes.io/) 了解更多。欲了解更多关于 Kubernetes 的内容，请自行探索。



## 监控和日志

监控和日志记录是运行维护中的重要组成部分，帮助你跟踪应用程序性能、检测问题并进行故障排除。

常见的工具包括 Prometheus（用于指标收集）、Grafana（用于可视化）、ELK Stack（Elasticsearch、Logstash、Kibana，用于日志管理）。

- 监控基础
  - 监控概念和重要性
  - Prometheus 指标收集
  - 应用程序日志查看
- 告警和可视化
  - 告警规则配置
  - 日志聚合和搜索（ELK）
  - Grafana 仪表板
- 高级分析
  - 监控配置优化
  - 分布式跟踪和 APM
  - 根因分析

[访问 Prometheus 官网](https://prometheus.io/) 和 [Grafana 官网](https://grafana.com/) 了解更多。欲了解更多关于监控和日志的内容，请自行探索。



## 安全

安全是运行维护中的关键方面，包括保护应用程序、数据和基础设施免受威胁。

常见的安全实践包括使用防火墙、SSL/TLS 加密、访问控制和定期更新。工具如 fail2ban（防止暴力破解）和 Let's Encrypt（免费 SSL 证书）。

- 安全基础
  - 加密和认证概念
  - 防火墙配置（ufw、iptables）
  - SSL/TLS 保护通信
- 访问控制
  - 最小权限原则
  - 定期更新和漏洞修补
  - 安全事件监控
- 高级安全
  - 容器安全和镜像扫描
  - 零信任架构
  - 渗透测试和漏洞评估

欲了解更多关于安全的内容，请自行探索。



## 云服务基础

云服务提供了可扩展的计算资源，帮助开发者快速部署和管理应用程序。主要的云提供商包括 AWS、Azure 和 Google Cloud。

云服务包括计算（EC2、VM）、存储（S3、Blob Storage）、数据库（RDS、Cosmos DB）等。掌握云服务的基础有助于在生产环境中部署应用。

- 云服务概念
  - IaaS、PaaS 和 SaaS
  - 云账户注册
  - 虚拟机创建
- 存储和数据库
  - 云存储使用
  - 负载均衡器配置
  - 云数据库基础
- 高级部署
  - 多区域部署
  - 无服务器计算（Lambda、Functions）
  - IaC 工具（Terraform）

[访问 AWS 文档](https://aws.amazon.com/documentation/) 了解更多。欲了解更多关于云服务的内容，请自行探索。



## 备份与恢复

备份和恢复策略是运维中至关重要的一环，用于保护数据免受意外删除、硬件故障、安全事件等威胁。一个好的备份策略应该包括自动化备份、异地存储、定期测试恢复流程等。

常见的备份方案包括数据库备份（mysqldump、pg_dump）、文件系统备份（rsync、tar）、快照备份（云服务商提供）等。还需要考虑备份的频率、保留策略和恢复时间目标（RTO）。

- 备份基础
  - 3-2-1 备份规则
  - 手动备份创建
  - 数据恢复流程
- 自动化备份
  - 定时备份设置（cron、systemd timers）
  - 备份类型（完整、增量、差异）
  - 远程存储
- 灾难恢复
  - CI/CD 中集成备份
  - 备份加密和压缩
  - 灾难恢复计划（DRP）和测试




## 机器人流程自动化 (RPA)

机器人流程自动化 (Robotic Process Automation, RPA) 是一种软件技术，用于自动化重复性、规则性的业务流程。通过模拟人类操作计算机的方式，RPA 可以处理数据输入、文件处理、电子邮件发送等任务，提高效率并减少错误。

常见的 RPA 工具包括 UiPath、Automation Anywhere 和 Microsoft Power Automate。这些工具允许你创建机器人来执行复杂的业务流程，而无需编程知识。

- RPA 基础概念
  - 机器人流程自动化定义
  - 适用场景和优势
  - 常见工具介绍
- 机器人创建
  - 流程录制和编辑
  - 数据处理和输入
  - 错误处理机制
- 部署和管理
  - 机器人部署
  - 监控和维护
  - 扩展和集成

[访问 UiPath 官网](https://www.uipath.com/) 了解更多。欲了解更多关于 RPA 的内容，请自行探索。

> 本篇文档由 [Fridemn](https://github.com/Fridemn) 编写。
> 封面图片来自 [Kevin](https://kevin56348.github.io/blog/)
> (●'◡'●)