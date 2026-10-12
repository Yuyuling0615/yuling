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
| `6430e3e` | docs(week05): add updated README with reflections |
| `9a95a84` | docs(week05): finalize README rename, clean temp files |
| `9ece378` | docs(week05): add pendulum screenshot |

## GitHub 仓库

https://github.com/Yuyuling0615/yuling

## 人机协同三反思

###Q 1. 意图清晰度反思 ：在今天的实验中，哪⼀次让 AI 编写代码时结果不符合预期？回看你当时输⼊的提示词，缺少了哪⼀项要素（⻆⾊/⽬ 标/约束/验收标准）？后来你如何补⻬的？
　　　A：生成的双摆模型摆动很慢，视觉效果差；约束条件没说清楚；添加描述词

Q2. 闭环控制反思 ：当遇到报错或动画停滞时，你是如何定位问题的？ AI 提出的修复⽅案中，你是否看懂了它是如何通过修改物理公式或边 界条件解决的？
　　　A：让ai自查：没有

Q3. 主体地位确认 ：作为⼈在回路之上（HOTL）的产品总设计师，今 天这套单摆物理模拟器中，哪些核⼼决策是由你决定的？哪些重复劳 动是由 AI 完成的？
　　　A：单摆的运动效果、整体最终展示效果由我确定；大量程序设计由ai完成