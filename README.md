# ninja 🥷

中文版 / English below

---

## 中文简介 🚀

**ninja** 是一个基于 **clash-mihomo** 与 **leaf** 再次深度修改的代理项目。  
它并不是对公版内核做简单封装，而是围绕协议栈、握手流程、验证机制与运行特征持续做了裁剪、重构与优化，目标是提供一个更简洁、更稳定、也更适合实际部署的核心实现。

### ✨ 主要特性

- **基于 clash-mihomo 与 leaf 深度再修改**  
  以两套成熟内核为基础，结合实际使用场景继续做定向优化与重构。

- **移除部分公版协议支持**  
  去掉不再需要的通用协议能力，减少冗余逻辑，让整体实现更聚焦。

- **简化加密算法设计**  
  对部分加密链路进行精简，降低不必要的复杂度，提升一致性与可维护性。

- **订阅混淆加密**  
  支持订阅加密混淆, 降低订阅链接暴露风险。

- **优化握手逻辑**  
  调整连接建立阶段的关键流程，改善握手效率与整体连接体验。

- **多层用户验证机制**  
  在接入与鉴权环节加入多层校验，用于增强访问控制与使用安全性。

- **弱化部分公版协议特征**  
  对默认实现中较明显的公版特征进行处理，减少通用化痕迹。

- **修改后的 Clash / Mihomo 等内核版本已在 Release 中提供**  
  当前再次修改后的相关核心版本，可直接在仓库的 Release 页面获取。

### 💻 客户端

当前已提供以下平台客户端：

- Windows
- Android
- macOS

一键加速客户端项目地址：  
https://github.com/kachetong1314/ninja-client

### ⚙️ 内核仓库

各版本内核下载地址：  
https://github.com/kachetong1314/ninja-core

---

## English 🌍

**ninja** is a custom proxy core built on top of **clash-mihomo** and **leaf**, with further deep modifications across the protocol stack, handshake flow, authentication model, and runtime behavior.

Rather than being a thin wrapper around public upstream cores, the project focuses on selective refactoring and practical optimization to deliver a cleaner, more controlled, and deployment-oriented implementation.

### ✨ Key Features

- **Further modified from clash-mihomo and leaf**  
  Built on top of two mature core projects, then selectively reworked and optimized for real-world deployment needs.

- **Removed unnecessary public protocol support**  
  Drops protocol implementations that are no longer needed, reducing redundant logic and keeping the core focused.

- **Simplified cryptographic design**  
  Streamlines parts of the encryption pipeline to reduce unnecessary complexity and improve maintainability.

- **obsfucated and encrypted subscription node content
  Drastically reduced open exposed subscription link leak / craw / search bot

- **Optimized handshake flow**  
  Refines connection setup behavior for better efficiency and a smoother connection experience.

- **Multi-layer user authentication**  
  Adds layered validation during connection and authorization stages for stronger access control.

- **Reduced generic public-protocol fingerprints**  
  Adjusts some of the more recognizable characteristics commonly found in public implementations.

- **Modified Clash / Mihomo-related builds are currently available in Releases**  
  Updated custom core builds can be downloaded directly from the repository Releases page.

### 💻 Clients

Current client support includes:

- Windows
- Android
- macOS

One-click acceleration client repository:  
https://github.com/kachetong1314/ninja-client

### ⚙️ Core Repository

Core downloads for different versions:  
https://github.com/kachetong1314/ninja-core
