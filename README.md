
# openspec-3gpp-analogy

# OpenSpec × 3GPP Conformance Specs
# OpenSpec × 3GPP 一致性测试规范映射
# 3gpp spec-to-openspec style
# protocol-agent-spec
# telcom-agent-spec
# rfc-agent-spec
# openspec x rfc

From TS 34.229 to AI Coding: writing specs like conformance tests.


This repository explores a simple but powerful idea:

**AI coding specs can be written like telecom conformance test specifications.**

In particular, the writing style used in spec-driven development (SDD), OpenSpec-like workflows, and agent-oriented coding has a strong structural resemblance to 3GPP UE conformance test specifications such as **TS 34.229**.

本仓库探索一个简单但有力量的观点：

**AI Coding 的 spec，可以借鉴电信领域的一致性测试规范来书写。**

尤其是，在 spec-driven development（SDD）、OpenSpec 风格工作流、以及 agent-oriented coding 中使用的 spec 写法，与 3GPP UE 一致性测试规范（如 **TS 34.229**）在结构上高度相似。

---

## Why this repository exists
## 为什么建立这个仓库

The core claim of this repository is:

> A good AI coding spec is not just product documentation.  
> It is closer to a **machine-oriented conformance specification**.

这个仓库的核心主张是：

> 一个好的 AI coding spec，本质上不只是产品文档，  
> 它更接近一种**面向机器的一致性规范**。

Both 3GPP conformance specs and AI coding specs aim to reduce ambiguity, increase testability, and make behavior executable.

3GPP 一致性规范与 AI coding spec 都在做同一件事：
- 降低歧义
- 提高可验证性
- 让行为描述变得可执行

---

## Core hypothesis
## 核心假设

We hypothesize that many successful AI coding spec patterns can be reinterpreted through the lens of 3GPP conformance testing:

我们提出如下假设：许多成功的 AI coding spec 写法，可以通过 3GPP 一致性测试规范的视角重新理解：

- scope definition / 范围界定
- implementation assumptions / 实现假设
- normative requirements / 规范性要求
- scenario-based behavior / 场景化行为
- verdict-oriented validation / 面向判定结果的验证
- testability as a first-class concern / 把可测试性作为一等公民

---

## A structural mapping
## 结构映射

| 3GPP conformance concept | AI coding / OpenSpec concept |
|---|---|
| Scope | Purpose / Scope |
| ICS / IXIT | Assumptions / Preconditions / Environment |
| Normative requirement | Requirement |
| Test purpose | Intent / Behavior objective |
| Test procedure | Scenario / Steps / Given-When-Then |
| Pass / Fail verdict | Acceptance criteria |
| ATS / Executability | Machine-readability / Agent executability |

| 3GPP 一致性测试概念 | AI coding / OpenSpec 对应概念 |
|---|---|
| Scope | Purpose / Scope |
| ICS / IXIT | Assumptions / Preconditions / Environment |
| Normative requirement | Requirement |
| Test purpose | Intent / 行为目标 |
| Test procedure | Scenario / Steps / Given-When-Then |
| Pass / Fail verdict | Acceptance criteria |
| ATS / Executability | Machine-readability / Agent executability |

---

## 3GPP references
## 3GPP 对标文档

### IMS
- **TS 34.229-1** — Protocol conformance specification
- **TS 34.229-2** — ICS specification
- **TS 34.229-3** — ATS
- **TS 34.229-4** — Enabler for IP multimedia applications testing
- **TS 34.229-5** — Protocol conformance using 5GS

### NAS
- **TS 34.123-1/2/3** — Early UE protocol conformance (including NAS-related behavior)
- **TS 36.523-1/2/3** — LTE UE protocol conformance
- **TS 38.523-1/2/3** — 5GS UE protocol conformance

### Mobility / MM / EMM / 5GMM
Not always a standalone spec family. Usually embedded inside NAS-oriented UE conformance specifications such as:
- TS 34.123-x
- TS 36.523-x
- TS 38.523-x

并不总是作为一个独立标准族存在，通常嵌入 NAS 相关 UE 一致性测试规范中。

### AT / ATC
- **TS 27.007** — AT command set for User Equipment (UE)

AT is not always represented by a standalone conformance-spec family.  
In many workflows it appears as a command/control interface inside broader UE conformance and ATS structures.

AT 并不总是对应一个独立的一致性测试标准族；很多时候它作为控制/接入接口出现在更大的 UE conformance / ATS 体系中。

### RRC
- **TS 34.123-x** — early UE protocol conformance
- **TS 36.523-1/2/3** — LTE RRC-related UE conformance
- **TS 38.523-1/2/3** — NR RRC-related UE conformance

### L2 / MAC
Usually not expressed as a fully standalone spec family analogous to IMS TS 34.229.
More often embedded in end-to-end UE protocol conformance:
- **TS 36.523-x**
- **TS 38.523-x**

MAC / L2 往往不是像 IMS TS 34.229 那样完全独立成族，而更多嵌入端到端 UE 协议一致性测试之中。

### PHY / RF
- **TS 34.121-1/2** — UE radio transmission and reception (FDD)
- **TS 34.122** — TDD
- **TS 38.521** family — NR UE radio transmission and reception conformance
- **TS 38.561** — NR UE TRP/TRS test methodologies for FR1

---

## What this repo is trying to build
## 这个仓库想构建什么

This repository is not only a document collection.
It aims to build a reusable method:

这个仓库不只是做文档整理，更想建立一套可复用方法：

1. **Map telecom conformance-writing patterns into AI coding specs**  
   把通信一致性测试规范的写法迁移到 AI coding spec

2. **Create OpenSpec-style templates inspired by TS 34.229 / 36.523 / 38.523**  
   基于 TS 34.229 / 36.523 / 38.523 设计 OpenSpec 风格模板

3. **Make specs more executable for coding agents**  
   让 spec 对 coding agent 更可执行

4. **Bridge requirements, tests, and implementation**  
   打通 requirement、test 与 implementation

---

## Initial insight
## 初始洞察

A surprisingly useful mental model is:

> AI coding spec = conformance-oriented behavior contract for an LLM.

一个非常有用的思维模型是：

> AI coding spec = 面向 LLM 的一致性行为契约

This means a spec should not merely “describe a feature”.
It should define:
- assumptions
- stimuli
- expected behavior
- validation points
- pass/fail boundaries

这意味着 spec 不应只是“描述功能”，还应明确：
- 假设条件
- 输入刺激
- 预期行为
- 验证点
- 通过/失败边界

---

## Repository roadmap
## 仓库路线图

- [ ] Collect canonical 3GPP spec examples
- [ ] Extract recurring writing patterns from TS 34.229 / 36.523 / 38.523
- [ ] Build an AI-coding spec template inspired by telecom conformance specs
- [ ] Provide example specs for NAS / IMS / RRC / L2 / PHY-style modules
- [ ] Compare with OpenSpec / SDD / agent workflows
- [ ] Publish bilingual methodology notes

- [ ] 收集典型 3GPP 样本
- [ ] 提炼 TS 34.229 / 36.523 / 38.523 的共性写法
- [ ] 产出 telecom-style AI spec 模板
- [ ] 给出 NAS / IMS / RRC / L2 / PHY 风格模块示例
- [ ] 与 OpenSpec / SDD / agent 工作流进行对比
- [ ] 持续发布中英文方法论笔记

---

## Non-goals
## 非目标

- This repository does **not** claim that OpenSpec was directly copied from 3GPP.
- This repository focuses on structural analogy and engineering usefulness.

- 本仓库**不主张** OpenSpec 直接来源于 3GPP。
- 本仓库关注的是结构类比与工程实用性。

---

## Why now
## 为什么是现在

Because AI coding is pushing software engineering toward a new requirement:

**Specs must be readable not only by humans, but also by agents.**

因为 AI coding 正在推动软件工程进入一个新阶段：

**spec 不仅要让人读懂，还要让 agent 读懂。**

Telecom conformance engineering has already spent decades solving a similar problem.

而通信一致性工程，其实早已在这个方向上积累了数十年的方法论。

---

## Contributing
## 参与贡献

Contributions are welcome if you are interested in:
- 3GPP conformance testing
- TTCN-3 / ATS thinking
- OpenSpec / SDD / spec-first development
- AI coding reliability
- executable specifications

如果你对以下主题感兴趣，欢迎参与：
- 3GPP 一致性测试
- TTCN-3 / ATS 思维
- OpenSpec / SDD / spec-first development
- AI coding 可靠性
- 可执行规范

---

## License
## 许可证

TBD