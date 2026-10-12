# Week 05 - 双摆混沌模拟器

## 实验信息

- **实验者**: 余玉玲
- **学号**: 7903126031
- **实验周次**: 第 5 周
- **实验主题**: 意图造物与 ReAct 闭环编程实战 — 双摆混沌模拟

## 项目概述

本实验从单摆简谐振动出发，逐步升级为具备混沌特性的双摆模拟器。采用 Runge-Kutta 4 阶数值积分精确求解双摆微分方程，支持实时参数调节、鼠标拖拽交互与彩虹拖尾可视化。

## 技术栈

- 纯原生 HTML5 Canvas，零外部依赖
- RK4 四阶数值积分（每帧 4 子步，dt 上限 0.02s）
- 双摆拉格朗日运动方程
- 鼠标 / 触摸拖拽交互
- HSL 彩虹渐变拖尾（300 点衰减）

## 目录结构

```
week05_pendulum_sim/
├── index.html          # 单文件交互应用（含 CSS + JS）
└── README.md           # 实验说明文档
```

## Git 提交历史

| Commit | 说明 |
|--------|------|
| `d90b246` | feat(week05): init pendulum experiment workspace |
| `f5c5f9f` | feat(week05): add pendulum simulator with canvas animation |
| `bab4cb0` | feat(week05): add interactive parameter controls and reset button |
| `b3d4ee0` | fix(week05): repair reset button scope and prevent physics jump on reset |
| `f655779` | feat(week05): upgrade to double pendulum with RK4, rainbow trail, and mouse drag |
| `1b4d89a` | tune(week05): increase swing speed range |
| `ba3bde3` | tune(week05): center pivot vertically, increase speed |

## 人机协同三反思

### 反思一：意图表达的精确性决定输出质量

在实验初期，我对需求描述较为笼统（如"做一个单摆"），AI 生成的代码虽然能运行，但缺少交互控制和视觉细节。当我改用结构化提示词（角色 / 目标 / 约束 / 验收标准）后，每次迭代的产出质量显著提升。**教训**：与 AI 协作时，约束条件越具体，返工次数越少。

### 反思二：Debug 阶段需要人机分工明确

重置按钮报错 `resetAnimation is not defined` 时，我最初只描述了现象。AI 通过根因分析定位到旧版 `onclick` 内联属性与新版 `addEventListener` 的缓存冲突，并顺带修复了 `lastTime = null` 导致的物理跳跃缺陷。**教训**：提供完整报错堆栈 + 预期行为，AI 才能做精准的根因定位而非表面修补。

### 反思三：AI 是加速器而非替代品

从单摆→双摆的升级涉及拉格朗日方程推导、RK4 积分实现、拖拽交互逻辑等复杂工作，AI 在 10 分钟内完成了我需要数小时才能写完的代码。但参数调优（摆角 170°、g=25、SCALE=0.006）仍需要我对物理直觉的判断。**教训**：AI 负责实现效率，人类负责方向决策与质量把关，两者互补才能产出工程级成果。

## GitHub 仓库

> [在此填入你的 GitHub 仓库链接]

## 运行方式

双击 `index.html` 即可在浏览器中打开，无需任何构建工具或服务器。
