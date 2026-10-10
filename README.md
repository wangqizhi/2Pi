 <div align="center">

# 2π

**2Pi — A GUI for Pi Coding Agent**

读作 Two Pi（图派）

*Another way to work with Pi.*

</div>

---

# 2Pi

**A modern desktop interface for [Pi Coding Agent](https://pi.dev/).**

**让 Pi 拥有第二种交互方式。**

2Pi 是一个基于 Pi Coding Agent 构建的独立图形客户端，旨在保留 Pi 原生 Agent 的核心能力，同时提供更直观、现代化、可视化的桌面开发体验。

## 为什么叫 2Pi？

在数学中：

**2π = τ ≈ 6.283185307179586**

`2π` 是两倍的圆周率，也等于数学常量 **τ（Tau）**。

在这个项目中，数字 **2** 并不代表性能翻倍，也不意味着比 Pi 更强大。

它代表的是 **Pi 的第二种交互形态**。

- **Pi**：原生 Coding Agent，通过终端与开发者交互，负责代码理解、工具调用和任务执行。
- **2Pi**：建立在 Pi 原生能力之上的图形交互层，让开发过程更加直观、透明和易于管理。

**我们不是要重新造一个 Pi，而是为 Pi 打开另一扇窗口。**

## 品牌设计理念

| 元素 | 设计定义 |
|---|---|
| 产品名称 | 2Pi |
| 视觉标识 | 2π |
| 英文标语 | Another way to work with Pi. |
| 中文标语 | 让 Pi 拥有第二种交互方式 |
| 核心概念 | Pi 的第二种交互形态 |
| 数学寓意 | 2π = τ |
| 品牌风格 | 极简、现代、专业、开放 |

### Logo 设计方向

Logo 以数字 `2` 和希腊字母 `π` 为核心视觉元素。

设计原则：

- **极简主义**：尽可能减少不必要的图形元素。
- **数学美感**：保留数学符号天然的几何特征。
- **视觉融合**：让数字 2 与 π 在笔画、比例或负空间上形成统一结构。
- **开发者风格**：简洁、克制、专业，不过度装饰。
- **跨平台适配**：适用于桌面图标、任务栏、终端及 GitHub 头像等不同场景。
- **品牌一致性**：产品名称使用 `2Pi`，视觉 Logo 使用 `2π`。

设计目标是让用户即使只看到简单的 `2π`，也能够快速识别这个项目。

## 产品愿景

**让 Pi 不再局限于终端，让开发者自由选择更适合自己的交互方式。**

2Pi 的目标不是替代 Pi Coding Agent，而是让其能力通过更加自然、直观的方式呈现。

通过现代化的桌面工作台，开发者可以更方便地管理会话、观察 Agent 执行过程、审查代码修改以及管理多个开发项目。

2Pi 希望在保持 Pi 简洁、开放和可扩展理念的同时，为开发者带来更加完整的图形化开发体验。

## 核心设计原则

### 1. Pi First

Pi 始终是 Agent 的核心。

2Pi 仅负责用户交互、状态呈现和工作区管理，不重复实现 Pi 已有的 Agent 能力。

### 2. Native Compatibility

优先采用 Pi 官方 RPC、SDK 等接口。

尽可能兼容 Pi 原生的模型配置、工具系统、扩展机制以及会话数据。

### 3. Local First

优先本地运行。

开发者能够直接管理本地项目、文件和 Pi Agent 进程，不强制依赖额外的云端服务。

### 4. Transparent Execution

Agent 的操作应当透明、可理解、可追踪。

清晰展示命令执行、工具调用、代码修改和运行状态，让开发者始终了解 Agent 正在做什么。

### 5. Developer Experience

减少不必要的交互步骤。

通过现代化 GUI 提升多会话管理、代码审查、项目切换及日常开发体验。

### 6. Extensibility

保持开放、模块化的架构，为多 Agent、远程连接以及更丰富的开发工具集成预留空间。

## 技术架构

2Pi 计划基于以下技术构建：

| 模块 | 技术方案 |
|---|---|
| 桌面框架 | Electron |
| 前端框架 | React |
| 开发语言 | TypeScript |
| Agent 核心 | Pi Coding Agent |
| Agent 通信 | Pi RPC |
| 通信协议 | JSONL / Standard I/O |
| UI 与主进程通信 | Electron IPC |
| 会话管理 | Pi 原生 Session |

### 架构设计

```text
┌───────────────────────────────────┐
│            2Pi GUI                │
│                                   │
│ Chat / Sessions / Diff / Files    │
│ Tools / Models / Workspace        │
└─────────────────┬─────────────────┘
                  │ Electron IPC
                  ▼
┌───────────────────────────────────┐
│       Electron Main Process       │
│                                   │
│ Process Manager / RPC Client      │
│ Configuration / Local Integration │
└─────────────────┬─────────────────┘
                  │ JSONL / stdio
                  ▼
┌───────────────────────────────────┐
│           Pi Coding Agent         │
│                                   │
│ Models / Tools / Extensions       │
│ Sessions / Context Management     │
└───────────────────────────────────┘
```

这种架构能够最大程度复用 Pi 原生能力，使 GUI 与 Agent 核心相互独立。

未来 Pi 更新时，2Pi 可以优先通过官方接口保持兼容，而不需要重新实现 Agent。

## 功能规划

以下功能目前属于项目规划，不代表已经实现。

### 基础能力

- [ ] Pi RPC 进程启动与管理
- [ ] Agent 聊天界面
- [ ] Markdown 与代码高亮
- [ ] 流式消息输出
- [ ] 工具执行状态展示
- [ ] Agent 中断与继续操作
- [ ] 模型选择与配置
- [ ] 思考等级切换

### 会话管理

- [ ] 历史会话浏览
- [ ] 创建与切换会话
- [ ] 恢复已有 Pi 会话
- [ ] 多会话管理
- [ ] 会话 Token 与费用统计
- [ ] 上下文压缩

### 开发者工具

- [ ] 项目工作区管理
- [ ] 文件浏览器
- [ ] 代码 Diff 可视化
- [ ] 命令执行过程展示
- [ ] 工具调用记录
- [ ] Git 状态集成
- [ ] 多项目切换

### 后续扩展

- [ ] 多 Agent 并行工作台
- [ ] Git Worktree 管理
- [ ] Pi Extensions 可视化管理
- [ ] 远程 Pi Agent 连接
- [ ] Windows / macOS / Linux 跨平台支持

## 与原生 Pi 的关系

2Pi 并不是 Pi Coding Agent 的替代品。

Pi 负责思考、执行和管理 Agent 的核心工作。

2Pi 则专注于如何更好地展示、控制和组织这些工作。

**Pi is the engine. 2Pi is another way to drive it.**

2Pi 是独立的第三方开源项目，并非 Pi 官方客户端，也不代表 Pi 官方开发团队。

## 项目状态

**Early Development / 早期开发阶段**

当前项目主要处于产品设计与技术验证阶段。

具体功能和实现方式可能随着开发推进而调整。

## 相关链接

- [Pi Coding Agent](https://pi.dev/)
- [Pi RPC Documentation](https://pi.dev/docs/latest/rpc)
- [Pi SDK Documentation](https://pi.dev/docs/latest/sdk)

---

<div align="center">

**2Pi · Another way to work with Pi.**

*Same Pi. A different perspective.*

</div>
