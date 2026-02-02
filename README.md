# Weavio

**Weavio is a cross-platform infrastructure framework for building modular and maintainable applications.**
**Weavio 是一个用于构建模块化、可维护应用的跨平台基础设施框架。**

Weavio is designed as a long-term foundation for applications that run across multiple platforms while keeping architecture clean, scalable, and testable.

Weavio 旨在成为一个长期稳定的应用基础底座，帮助你在多平台环境下保持架构清晰、可扩展、易测试。

---

## Why Weavio ｜ 为什么需要 Weavio

### English

Modern applications often suffer from:

* Duplicated infrastructure across Android, iOS, and other platforms
* Tight coupling between business logic and platform APIs
* Frameworks that mix UI, business logic, and infrastructure
* Increasing architectural complexity as projects scale

Weavio addresses these problems by acting as a **pure infrastructure layer**.

### 中文

现代应用常常面临以下问题：

* Android、iOS 等平台之间的基础设施代码大量重复
* 业务逻辑与平台 API 强耦合，难以测试和演进
* 框架同时承担 UI、业务和基础设施职责，边界混乱
* 项目规模增长后，架构复杂度失控

Weavio 通过提供一个**纯粹的基础设施层**来解决这些问题。

---

## What Weavio Is / Is Not ｜ Weavio 是什么 / 不是什么

### ✅ What Weavio Is

* A cross-platform infrastructure foundation
* Modular and opt-in
* Lifecycle-aware
* Platform-agnostic at the core

### ❌ What Weavio Is Not

* Not a UI framework
* Not a business framework
* Not an all-in-one SDK

---

### ✅ Weavio 是什么

* 跨平台的基础设施框架
* 模块化、按需引入
* 具备明确生命周期管理
* 核心层不依赖任何平台

### ❌ Weavio 不是什么

* 不是 UI 框架
* 不是业务框架
* 不是“全家桶 SDK”

---

## Design Philosophy ｜ 设计理念

### Infrastructure First ｜ 基建优先

**English**
Weavio focuses exclusively on infrastructure concerns:

* Logging
* Networking
* Storage
* Runtime environment
* Platform abstraction

UI and business logic are intentionally left to upper layers.

**中文**
Weavio 只关注基础设施问题：

* 日志
* 网络
* 存储
* 运行时环境
* 平台能力抽象

UI 和业务逻辑被有意留给上层处理。

---

### Modular Capabilities ｜ 能力模块化

**English**
Each capability is an independent module:

* No hidden dependencies
* No global god object
* No forced feature inclusion

**中文**
每一项能力都是独立模块：

* 没有隐式依赖
* 没有超级全局对象
* 不强制引入不需要的功能

---

### Centralized Lifecycle ｜ 生命周期集中管理

> **Capabilities are modular. Lifecycle is centralized.**

**English**

* Capabilities expose their own APIs
* Initialization and shutdown are coordinated by `WeavioRuntime`

**中文**

* 各能力模块只暴露自己的 API
* 初始化与释放由 `WeavioRuntime` 统一管理

---

## Architecture Overview ｜ 架构概览

```
Application / Feature Modules
        ↑
------------------------------
Weavio Capabilities
(logging / network / storage)
------------------------------
Weavio Runtime
------------------------------
Weavio Core
------------------------------
Platform Adaptation (Android / iOS)
```

---

## Core Modules ｜ 核心模块

### Weavio Core

* Pure Kotlin
* No platform dependencies
* Shared primitives and abstractions

---

### Weavio Runtime

* Central lifecycle coordinator
* Component registration
* Environment management

---

### Capability Modules

* `weavio-logging`
* `weavio-network`
* `weavio-storage`

Each module:

* Has its own public API
* Registers itself via `RuntimeComponent`

---

## Example Usage ｜ 使用示例

### Initialization

```kotlin
WeavioRuntime.start {
    register(LoggingComponent())
    register(NetworkComponent(...))
}
```

### Logging

```kotlin
Logger.d("Network", "Request started")
```

---

## Guiding Principles ｜ 指导原则

* Infrastructure over convenience
* Explicit over implicit
* Modularity over monoliths
* Long-term maintainability over short-term speed

---

## Vision ｜ 愿景

**English**
Weavio aims to be a stable and predictable infrastructure foundation that teams can rely on for years.

**中文**
Weavio 的目标是成为一个多年可依赖、稳定、可预期的应用基础设施底座。

---

## License

Apache-2.0 (or your preferred license)
