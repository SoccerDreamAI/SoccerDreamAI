# SoccerDream AI

**一个会自己吵架、逐条交叉质证、发布结论前先自我复盘的 AI 专家团。**

[English](README.md) · [简体中文](README.zh-CN.md)

[![源码可见](https://img.shields.io/badge/状态-源码可见-orange.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md)
[![非博彩产品](https://img.shields.io/badge/属性-研究框架_非博彩产品-red.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md)
[![License: BUSL-1.1](https://img.shields.io/badge/license-BUSL--1.1-blue.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md)

[官网](https://soccerdreamai.com) · [框架仓库](https://github.com/SoccerDreamAI/soccerdream-experts) · [为什么不能取平均](https://dev.to/soccerdreamai/why-a-multi-agent-system-must-not-average-3p5d) · [讨论区](https://github.com/SoccerDreamAI/soccerdream-experts/discussions)

---

## 我们在做什么

大多数「AI 分析」产品给你一个模型、一个自信的答案。凡是错一次代价很高的问题，
这个形状都是错的——那份自信在做的事，比分析本身还多。

所以我们公开的是**团队的形状**：几个先验真正不同的专家，一套结构化的分歧协议，
以及一个有权推翻结论的评审环节。

- 他们遵守的每一条规则，你都能读到
- 你可以用同一份 schema 搭自己的团队
- 你看不到的，是我们认为属于产品的部分

## 只有一条规则

> **分歧只升级，绝不取平均。**

取平均这个操作有个反直觉的性质：**专家意见一致时，它等于什么都没做；意见分歧时，
它才满功率运转。** 这恰好是反的。

因为两个人意见一致时，平均不改变任何东西；而当两个有依据的读者互相矛盾时，
这一轮里唯一有信息量的事实就是「他们矛盾了」——平均值会把这个事实抹掉，
产出一个**没人提出过、也没人会为之辩护**的结论。

所以分歧不进平均，进质询。双方要么各自举出证据站住，要么**书面撤回**，
而撤回这件事本身要记录在案，因为它才是那一轮的真实产出。两边都站住，
则标记为 `unresolved` 原样输出。

一句诚实的「这局我们没定下来」，好过一个编出来的中间值。

## 什么公开，什么不公开

| | 内容 | 是否公开 |
|:--|:--|:--:|
| 人设 | 四个专家，遵守 `先验 → 方法 → 证据标准 → 拒答` 四段契约 | ✅ |
| 编排 | `teams/` schema 与可直接运行的示例 | ✅ |
| 推理过程 | 架构文档，含我们踩过的五个坑 | ✅ |
| 训练词 | 让这些人设真正起作用的模型专属措辞 | ❌ |
| 评估权重 | 一条结论要通过评审必须跨过的门槛 | ❌ |
| 数据链路 | 实时适配、归一化与结算逻辑 | ❌ |

本仓库**源码可见，非开源**。这句话写在第一行，而不是让你装完之后自己发现——
一个看起来完整、实际不完整的仓库，对项目的伤害比缺的那部分代码更大。

这不是谦虚。人设单独拿出来就有用；让它可靠的那部分，我们留下了。

## 从这里开始

1. **先读推理** —— [为什么多智能体不能取平均](https://dev.to/soccerdreamai/why-a-multi-agent-system-must-not-average-3p5d)（英文长文）
2. **读架构** —— [docs/zh-CN/architecture.md](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/docs/zh-CN/architecture.md)
3. **搭一个团队** —— [teams/](https://github.com/SoccerDreamAI/soccerdream-experts/tree/main/teams)
4. **晒你的配置** —— [讨论区](https://github.com/SoccerDreamAI/soccerdream-experts/discussions/4)

如果只有三十秒：最容易踩的坑是**独立性从运行时泄漏**。提示词看起来很干净，
但每个成员其实在读同一块共享缓冲——你付了四份钱，收到一份。

---

<sub>这是一个分析方法框架。它不预测结果、不构成建议，也不用于任何形式的投注。
SoccerDream AI 与 SoccerDream Expert Team 均为未注册商标；fork 必须改名，
且不得暗示获得官方背书。详见
[TRADEMARK.md](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/TRADEMARK.md)。</sub>
