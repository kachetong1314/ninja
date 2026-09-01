<div align="center">

# 🥷 NINJA 2.0

### Advanced Multi-Layer Networking Core

### 下一代多层网络传输与客户端解决方案

**Mihomo · Leaf · Ninja Core · Tunnel Layer · Multi-Platform**

<br>

[![Ninja 2.0](https://img.shields.io/badge/Ninja-2.0-black?style=for-the-badge)](https://app.ninjav2.dev/)
[![Platforms](https://img.shields.io/badge/Platforms-8+-blue?style=for-the-badge)](https://app.ninjav2.dev/)
[![Core](https://img.shields.io/badge/Core-Mihomo%20%2B%20Leaf-purple?style=for-the-badge)](https://github.com/kachetong1314/mihomo-ninja/releases)
[![OpenWrt](https://img.shields.io/badge/OpenWrt-Supported-success?style=for-the-badge)](https://app.ninjav2.dev/)

<br>

**中文 ｜ [English](#english)**

<br>

> **Ninja 2.0 不只是一个客户端，也不只是对公版核心进行重新封装。**
> 它是一套围绕协议实现、连接建立、身份验证、订阅分发、隧道传输和多平台客户端重新构建的完整网络技术体系。

</div>

---

# 🥷 Ninja 2.0

## 新一代多层网络传输架构

**Ninja 2.0** 是基于 **Mihomo / Clash-Mihomo** 与 **Leaf** 持续深度修改和独立演进的网络核心与客户端技术方案。

从最初版本开始，Ninja 就没有将目标定位为简单的 UI 封装或传统公版核心二次打包。

在 Ninja 2.0 中，我们进一步对：

* 协议栈实现
* 连接握手
* 握手时序
* 身份验证
* 订阅分发
* 流量形态
* 隧道封装
* 客户端运行逻辑
* 多平台网络适配

进行了重新设计与持续优化。

最终形成了一套由 **Ninja Core + Tunnel Layer + Client Runtime** 共同组成的多层网络架构。

---

# ⚡ Ninja 2.0 Architecture

```text
┌───────────────────────────────────────────────┐
│                 Ninja Client                  │
│                                               │
│   Windows · macOS · Android · Linux · iOS     │
│             tvOS · OpenWrt                    │
└──────────────────────┬────────────────────────┘
                       │
                       ▼
┌───────────────────────────────────────────────┐
│                  Ninja Core                   │
│                                               │
│  Protocol Stack · Authentication · Routing    │
│  Subscription · Connection Management         │
└──────────────────────┬────────────────────────┘
                       │
                       ▼
┌───────────────────────────────────────────────┐
│               Ninja Tunnel Layer              │
│                                               │
│  Encapsulation · Transport Profile            │
│  Timing · Session Behavior · Parameters       │
└──────────────────────┬────────────────────────┘
                       │
                       ▼
┌───────────────────────────────────────────────┐
│                Network Transport              │
└───────────────────────────────────────────────┘
```

传统客户端通常采用：

```text
Client → Proxy Protocol → Server
```

Ninja 2.0 则进一步将核心网络通信与传输层进行拆分：

```text
Ninja Client
      ↓
Ninja Core
      ↓
Tunnel Layer
      ↓
Network Transport
      ↓
Server
```

这使 Ninja 的协议核心、身份验证、传输方式和客户端实现不再强绑定于单一网络层。

---

# ✨ Ninja 2.0 核心特性

## 🧠 深度修改的 Ninja Core

Ninja Core 基于 **Mihomo / Clash-Mihomo** 与 **Leaf** 的成熟网络实现继续开发。

但 Ninja 并不是简单 Fork。

我们针对实际部署需求，对部分协议实现、连接管理、验证流程以及客户端运行逻辑进行了持续修改。

包括：

* 网络协议栈调整
* 连接生命周期管理
* 客户端与核心通信
* 节点配置处理
* 用户验证
* 连接状态管理
* 多平台网络适配

使 Ninja Core 逐渐形成独立于普通公版核心的实现体系。

---

## 🛡️ 协议与流量形态优化

很多通用网络协议在长期运行后，会形成相对固定的：

* 数据交互模式
* 连接建立行为
* 数据包节奏
* 初始化流程
* 客户端实现特征

Ninja 2.0 对部分固定行为进行了重新设计。

目标并不是简单更换协议名称，而是让不同网络组件之间具备更大的实现自由度和可配置能力。

---

## 🤝 握手逻辑优化

Ninja 2.0 对连接建立阶段进行了进一步调整。

包括：

* 握手流程
* 初始化逻辑
* 数据交互顺序
* 会话建立方式
* 部分字段处理
* 客户端与服务端协商行为

相比完全采用默认公版实现，Ninja Core 可以根据自身客户端和服务端体系进行独立优化。

---

## ⏱️ 握手时序优化

网络连接不仅由“发送什么数据”组成。

**数据在什么时间发送、以什么顺序发送、不同阶段如何衔接，同样属于连接行为的一部分。**

Ninja 2.0 对连接初始化阶段的部分时序逻辑进行了重新设计，包括：

```text
Connection Init
      ↓
Authentication
      ↓
Session Establishment
      ↓
Tunnel Initialization
      ↓
Data Transport
```

进一步降低整个网络栈对于单一固定初始化流程的依赖。

---

# 🕳️ Ninja Tunnel Layer

## Ninja 2.0 的重要架构变化

Ninja 2.0 引入了独立的：

### **Ninja Tunnel Layer**

客户端启动后，不再只是简单地：

```text
Proxy Core → Internet
```

而是通过：

```text
Ninja Core
    ↓
Ninja Tunnel Layer
    ↓
Network Transport
```

完成最终网络通信。

---

## ⚙️ 可配置隧道参数

Tunnel Layer 并不是完全固定的黑盒。

根据不同部署需求，部分：

* Transport Parameters
* Session Parameters
* Connection Behavior
* Timing Profile
* Encapsulation Parameters
* Runtime Settings

可以进行调整。

因此不同部署环境并不要求采用完全一致的网络行为配置。

---

## 🌐 独立的传输形态

通过 Tunnel Layer，Ninja Core 不需要直接暴露所有底层连接行为。

核心负责：

```text
Protocol
Authentication
Routing
Connection Management
Subscription
```

Tunnel Layer 负责：

```text
Transport
Encapsulation
Session
Timing
Network Delivery
```

两者互相解耦。

这种设计使 Ninja 2.0 与传统“客户端 + 单一代理协议”的模式存在明显架构差异。

---

# 🔐 多层身份验证

Ninja 2.0 将身份验证设计为整个网络体系的一部分。

验证可以存在于不同阶段：

```text
Account
   ↓
Subscription
   ↓
Client
   ↓
Ninja Core
   ↓
Protocol Authentication
   ↓
Tunnel
```

可以根据不同商业部署需求构建多层访问控制体系。

---

# 🔏 加密订阅与混淆分发

传统订阅通常直接返回完整节点内容。

一旦订阅地址发生：

* 意外泄露
* 被自动扫描
* 被搜索系统索引
* 被第三方抓取
* 被日志系统记录

节点信息可能直接暴露。

Ninja 提供独立的订阅内容处理机制。

```text
User
 ↓
Authentication
 ↓
Subscription API
 ↓
Encrypted / Obfuscated Payload
 ↓
Ninja Client
 ↓
Local Decode
```

客户端获取后再由 Ninja 自身逻辑进行处理。

从而减少传统明文订阅直接暴露完整节点配置所带来的风险。

---

# 🧩 多层网络体系

Ninja 2.0 的设计目标并不是创造另一个“协议名称”。

而是建立：

```text
Client Layer
      +
Core Layer
      +
Authentication Layer
      +
Protocol Layer
      +
Tunnel Layer
      +
Transport Layer
```

各层可以独立演进的网络架构。

因此未来 Ninja 可以在不重新设计整个客户端的情况下持续调整：

* Core
* Tunnel
* Authentication
* Transport
* Subscription
* Runtime

---

# 🚀 性能与稳定性

Ninja 2.0 同时关注网络特征与实际连接体验。

优化方向包括：

### Connection

* 更合理的连接生命周期
* 更稳定的连接初始化
* 网络切换处理
* 断线恢复
* Session 管理

### Runtime

* Core 运行状态管理
* 客户端与核心生命周期同步
* 本地网络环境检测
* DNS 处理
* 网络可用性检测

### Deployment

* Desktop
* Mobile
* Router
* Linux Server / Client

针对不同设备采用不同的运行策略。

---

# 🖥️ 全平台客户端

Ninja 2.0 已经形成完整的多平台客户端体系。

<div align="center">

| Platform           | Support |
| ------------------ | ------- |
| 🪟 Windows         | ✅       |
| 🍎 macOS           | ✅       |
| 🤖 Android         | ✅       |
| 🐧 Linux           | ✅       |
| 🌀 Debian / Ubuntu | ✅       |
| 📡 OpenWrt         | ✅       |
| 📱 iOS             | ✅       |
| 📺 Apple tvOS      | ✅       |

</div>

---

# 📥 Ninja 2.0 客户端下载

<div align="center">

## 🚀 Official Ninja 2.0 Download Portal

### https://app.ninjav2.dev/

**Windows · macOS · Android · Linux · OpenWrt · iOS · tvOS**

</div>

不同操作系统对应的安装包、客户端版本以及安装说明统一通过 Ninja 2.0 下载页面发布。

---

# ⚙️ Ninja Core Downloads

修改后的 **Mihomo / Clash Ninja Core**：

### https://github.com/kachetong1314/mihomo-ninja/releases

历史客户端及相关项目：

### https://github.com/kachetong1314/ninja/releases/

---

# 🆚 Ninja 2.0 与传统代理客户端

| Architecture                   | Traditional Client | Ninja 2.0 |
| ------------------------------ | -----------------: | --------: |
| Public Core Wrapper            |                 常见 |         ❌ |
| Independent Core Modifications |                 部分 |         ✅ |
| Multi-layer Authentication     |                 较少 |         ✅ |
| Encrypted Subscription         |                 部分 |         ✅ |
| Custom Subscription Format     |                 较少 |         ✅ |
| Handshake Optimization         |               默认实现 |         ✅ |
| Timing Optimization            |               默认实现 |         ✅ |
| Independent Tunnel Layer       |               通常没有 |         ✅ |
| Configurable Tunnel Parameters |               通常没有 |         ✅ |
| Desktop Clients                |                  ✅ |         ✅ |
| Mobile Clients                 |                  ✅ |         ✅ |
| Router Integration             |                 部分 |         ✅ |
| iOS / tvOS                     |                 部分 |         ✅ |
| Private Deployment             |                 部分 |         ✅ |

---

# 🏢 Ninja 2.0 Commercial Solution

## 商业授权与完整技术解决方案

Ninja 2.0 不仅提供公开版本。

针对具有：

* 商业运营
* 私有部署
* 企业网络
* 独立品牌
* 自有用户系统
* 多平台客户端
* 定制网络架构

需求的团队，我们可以提供完整的 **Ninja 2.0 商业授权与技术解决方案**。

---

## 可提供的解决方案

### 🥷 Ninja Protocol

* Ninja 2.0 协议授权
* 协议层定制
* 认证机制适配
* 服务端适配
* Core 定制

### 🕳️ Tunnel Solution

* Ninja Tunnel Layer
* Tunnel 参数定制
* 网络传输策略
* Session 行为调整
* 部署环境适配

### 💻 Client Solution

提供：

* Windows
* macOS
* Android
* Linux
* Debian / Ubuntu
* OpenWrt
* iOS
* Apple tvOS

客户端技术方案。

---

### 🔐 Authentication

可与现有：

* 用户系统
* Subscription System
* API
* Billing
* Device Management
* License System

进行整合。

---

### 🎨 White Label

可以根据商业需求提供：

* 品牌定制
* Logo
* UI
* Domain
* Client Name
* Package Name
* API Endpoint
* Download Portal

等独立品牌方案。

---

### ☁️ Private Deployment

支持根据实际业务架构进行：

* 私有服务器部署
* API 整合
* 客户端部署
* Core 部署
* Tunnel 部署
* 用户系统整合

---

### 🛠️ Long-Term Support

商业方案可以根据项目需求提供：

* Core 更新
* Client 更新
* 系统维护
* API 适配
* 新平台支持
* Bug Fix
* 技术升级

等长期技术支持。

---

# 🤝 商业合作

如果您希望购买一整套：

### **Ninja 2.0 Protocol License**

### **Ninja Core**

### **Ninja Tunnel**

### **Multi-Platform Clients**

### **Private Deployment**

### **Complete Technical Solution**

欢迎联系我们进一步沟通。

我们可以根据：

* 用户规模
* 服务器架构
* 客户端平台
* 网络环境
* 品牌需求
* API 架构
* 商业模式

制定对应的 Ninja 2.0 技术方案。

---

<div align="center">

# NINJA 2.0 🥷

### Core. Tunnel. Client.

**One Architecture. Multiple Platforms.**

### https://app.ninjav2.dev/

</div>

---

# English

<div align="center">

# 🥷 NINJA 2.0

### Advanced Multi-Layer Networking Architecture

**Ninja Core · Tunnel Layer · Authentication · Multi-Platform Clients**

</div>

---

## Overview

**Ninja 2.0** is a deeply customized networking core and client ecosystem built upon **Mihomo / Clash-Mihomo** and **Leaf**.

Ninja is not designed as a simple graphical wrapper around an upstream public core.

The project continuously modifies and evolves multiple parts of the networking stack, including:

* Protocol implementation
* Connection establishment
* Handshake behavior
* Handshake timing
* Authentication
* Subscription delivery
* Traffic profiles
* Tunnel encapsulation
* Client runtime behavior
* Cross-platform networking

Ninja 2.0 introduces a layered architecture consisting of:

```text
Ninja Client
     ↓
Ninja Core
     ↓
Ninja Tunnel Layer
     ↓
Network Transport
```

This architecture separates protocol logic from the underlying transport implementation.

---

# ✨ Key Features

## Deeply Customized Ninja Core

Ninja Core evolves from mature networking projects including Mihomo and Leaf while introducing extensive modifications for real-world deployment scenarios.

Development areas include:

* Protocol stack behavior
* Connection lifecycle
* Authentication
* Subscription processing
* Client/core communication
* Network state management
* Cross-platform integration

---

## Protocol & Traffic Profile Optimization

Generic implementations often share relatively consistent runtime and connection characteristics.

Ninja 2.0 redesigns selected behaviors within the networking stack to provide a more independently controlled implementation.

Rather than relying entirely on upstream defaults, protocol behavior can evolve together with the Ninja client and server ecosystem.

---

## Handshake Optimization

Connection-establishment logic has been further refined in Ninja 2.0.

This includes selected changes to:

* Initialization
* Handshake sequencing
* Session establishment
* Field processing
* Client/server negotiation
* Connection lifecycle

---

## Handshake Timing

Network behavior is not determined only by the content of packets.

Timing, sequencing, session initialization, and interaction patterns also influence the overall behavior of a connection.

Ninja 2.0 therefore introduces additional control over selected timing and initialization behavior.

---

# 🕳️ Ninja Tunnel Layer

One of the major architectural changes introduced in Ninja 2.0 is the dedicated:

## **Ninja Tunnel Layer**

Traditional clients commonly use:

```text
Client
   ↓
Proxy Protocol
   ↓
Server
```

Ninja 2.0 instead follows a layered model:

```text
Ninja Client
     ↓
Ninja Core
     ↓
Tunnel Layer
     ↓
Network Transport
```

The tunnel layer separates protocol processing from network transport.

---

## Tunable Tunnel Parameters

Selected tunnel characteristics can be configured according to deployment requirements.

These may include:

* Transport parameters
* Session parameters
* Connection behavior
* Timing profiles
* Encapsulation settings
* Runtime configuration

This allows different deployments to use transport configurations appropriate to their own network architecture.

---

## Independent Transport Architecture

Ninja Core can focus on:

```text
Protocol
Authentication
Routing
Subscription
Connection Management
```

while Ninja Tunnel handles:

```text
Transport
Encapsulation
Sessions
Timing
Network Delivery
```

This separation provides significantly greater architectural flexibility than conventional single-protocol client designs.

---

# 🔐 Multi-Layer Authentication

Authentication can be implemented across multiple stages:

```text
Account
   ↓
Subscription
   ↓
Client
   ↓
Ninja Core
   ↓
Protocol Authentication
   ↓
Tunnel
```

This architecture provides deployment operators with greater control over user access and service authorization.

---

# 🔏 Encrypted Subscription Delivery

Traditional subscription systems often expose complete node configuration through a single plaintext subscription endpoint.

Ninja can instead deliver subscription data through its own encrypted and obfuscated payload format:

```text
User
 ↓
Authentication
 ↓
Subscription API
 ↓
Encrypted Payload
 ↓
Ninja Client
 ↓
Local Processing
```

This reduces unnecessary exposure of complete configuration data when subscription links are accidentally leaked, logged, indexed, or collected by automated systems.

---

# 💻 Platform Support

Ninja 2.0 currently supports:

| Platform        | Support |
| --------------- | ------- |
| Windows         | ✅       |
| macOS           | ✅       |
| Android         | ✅       |
| Linux           | ✅       |
| Debian / Ubuntu | ✅       |
| OpenWrt         | ✅       |
| iOS             | ✅       |
| Apple tvOS      | ✅       |

---

# 📥 Download Ninja 2.0

<div align="center">

## Official Client Portal

### https://app.ninjav2.dev/

**Windows · macOS · Android · Linux · OpenWrt · iOS · tvOS**

</div>

---

# ⚙️ Ninja Core

Modified Mihomo / Clash Ninja Core releases:

### https://github.com/kachetong1314/mihomo-ninja/releases

Legacy Ninja clients and related projects:

### https://github.com/kachetong1314/ninja/releases/

---

# 🏢 Commercial Licensing

Ninja also provides **commercial licensing and complete technical solutions for Ninja 2.0**.

Solutions can include:

* Ninja 2.0 protocol licensing
* Customized Ninja Core
* Ninja Tunnel Layer
* Server-side integration
* Authentication infrastructure
* Encrypted subscription systems
* Windows client
* macOS client
* Android client
* Linux client
* OpenWrt integration
* iOS client
* Apple tvOS client
* API integration
* Account-system integration
* Private deployment
* White-label client development
* Long-term maintenance
* Technical support

Organizations interested in deploying a complete Ninja 2.0 architecture may contact us to discuss:

* Deployment scale
* Infrastructure
* Client platforms
* Network requirements
* Branding
* API architecture
* Customization
* Commercial licensing

---

<div align="center">

# NINJA 2.0 🥷

### Core · Tunnel · Authentication · Client

**A complete multi-platform networking architecture.**

### https://app.ninjav2.dev/

</div>
