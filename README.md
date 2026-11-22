# 回归第一性原理：从摩尔定律到韬定律

从摩尔定律（1965）到韬定律（2026），半导体"缩放"这条路走了六十年。这份资料库把每一环
——以及它们的原始论文、译介和思考——整理在一起。

---

## 时间线

| 年份 | 事件 |
|------|------|
| 1965 | 摩尔定律 |
| 1974 | Dennard 缩放定律 |
| 1980 | Mead–Conway VLSI 方法学 |
| 1980s– | EDA（Synopsys / Cadence）|
| 2005 | Dennard 失效 → 多核转向 |
| 2010s– | 先进封装 / Chiplet |
| 2026 | 韬定律（τ 缩放）|

---

## 一、摩尔定律（1965）

戈登·摩尔 1965 年 4 月 19 日发表在《Electronics》杂志的论文
《Cramming More Components onto Integrated Circuits》（把更多元件塞进集成电路）。

- [moore_1965.pdf](moore/moore_1965.pdf) — 原始论文 PDF（IEEE 重印版）
- [moore_1965.txt](moore/moore_1965.txt) — 提取的纯文本
- [moore_1965_zh.md](moore/moore_1965_zh.md) — 中文全文翻译

**关键预测**：最低成本下的复杂度约每年翻一番，到 1975 年每个集成电路达 6.5 万个元件。

**三点澄清**：① "摩尔定律"一词摩尔本人从未使用，是 Carver Mead 在 1970 年代命名；②
原始预测是"每年翻番"，1975 年摩尔修正为"每两年翻番"；③ 摩尔说的是"元件数"，非狭义
的"晶体管数"。

**1975 年修正论文**：*Progress in Digital Integrated Electronics*（IEDM 1975，
DOI 10.1109/IEDM.1975.188490，IEEE 付费，未收录）。

---

## 二、Dennard 缩放定律（1974）

摩尔定律说"密度翻倍"，但没说"缩小了功耗怎么办"。IBM 的 **Robert Dennard** 1974 年在
论文 *Design of ion-implanted MOSFET's with very small physical dimensions* 中回答：
把晶体管所有尺寸与电压按同一比例缩小，就能同时得到密度翻倍、速度提升，而**单位面积功耗
密度保持不变**——这就是半导体黄金时代（约 1974–2005）"免费午餐"的物理基础。约 2005 年
因漏电失效，CPU 频率随之封顶。

- [Dennard_1974_ion-implanted_MOSFET.pdf](dennard/Dennard_1974_ion-implanted_MOSFET.pdf) — 原始论文 PDF（13 页）
- [Dennard_定律介绍.md](dennard/Dennard_定律介绍.md) — 中文介绍
- [多核转向_免费午餐的终结_介绍.md](dennard/多核转向_免费午餐的终结_介绍.md) — 2005 年 Dennard 失效的直接后果

---

## 三、Carver Mead 与现代 VLSI 设计方法（1980）

"摩尔定律"这一名称正是加州理工教授 **Carver Mead** 命名的。他与 Lynn Conway 合著的
《Introduction to VLSI Systems》（1980）引发了 **Mead–Conway VLSI 设计革命**：把芯片
设计从底层工艺中抽象出来（λ 设计规则、层次化/结构化设计），让普通计算机科学家也能设计
大规模芯片——现代芯片设计流程的源头。

- [Carver_Mead_介绍.md](mead_conway/Carver_Mead_介绍.md) — Carver Mead 工作全貌的中文介绍

### λ 设计规则

在 Mead–Conway 之前，设计规则是**绝对尺寸**（每层金属多宽、间距多少，全是具体微米数值，
且每一代工艺都不一样），设计死死绑定工艺、不可移植。Mead–Conway 的革新是：把所有几何
尺寸都表示成**单一参数 λ 的整数倍**（λ = 最小特征尺寸的一半），例如最小线宽 = 2λ、
最小间距 = 3λ。于是设计不绑定工艺，换工艺只需按比例缩放 λ。

### 教材与文献

- [V1.pdf](mead_conway/V1.pdf) — 《Introduction to VLSI Systems》第一卷（系统设计）
- [V2.pdf](mead_conway/V2.pdf) — 第二卷（电路设计）
- [V3.one-sided.pdf](mead_conway/V3.one-sided.pdf) — 第三卷（器件与物理，单面版）
- [The_Design_of_VLSI_Design_Methods.pdf](mead_conway/The_Design_of_VLSI_Design_Methods.pdf) — Conway《The Design of VLSI Design Methods》（ESSCIRC 1982）

### MPC：多项目晶圆

Mead–Conway 革命之所以是"革命"而非一家公司的内部成果，关键在于 **MPC（Multi-Project
Chip）**——把多个设计拼到同一片晶圆流片、分摊成本，让大学和学生也负担得起真实流片。

- [MPC_多项目晶圆_介绍.md](mead_conway/MPC_多项目晶圆_介绍.md) — 中文介绍
- [MIT78.pdf](mead_conway/mpc/MIT78.pdf) — MIT 1978 年 VLSI 课程档案（MPC 源头）
- [ImpDoc79.pdf](mead_conway/mpc/ImpDoc79.pdf) — MPC79 实施文档
- [MPC79ChipPhotos.pdf](mead_conway/mpc/MPC79ChipPhotos.pdf) — MPC79 芯片照片
- [MPCAdv.pdf](mead_conway/mpc/MPCAdv.pdf) — MPC 后续推进文档

> 来源：Lynn Conway 官网免费提供的 VLSI 教材与历史档案，英文原文，未做翻译。

---

## 四、EDA：从方法学到工具（1980s 至今）

Mead–Conway 提供的是**方法学**（抽象、λ 规则、层次化设计），而 **EDA（电子设计自动化）**
把这套方法变成设计师每天使用的软件工具链——逻辑综合、布局布线、仿真验证、物理验证。
核心玩家是 **Synopsys**（1986，逻辑综合起家）、**Cadence**（1988）与 **Siemens EDA
（原 Mentor Graphics）**。

何庭波韬定律论文第 7 章明确点出：现有 EDA 是"为 2D 平面时代开发的"，无法适配逻辑折叠
的 3D 堆叠，需要"τ 原生、3D 原生"的下一代工具链。

- [EDA_电子设计自动化_介绍.md](eda/EDA_电子设计自动化_介绍.md) — EDA 的中文介绍

---

## 五、先进封装与 Chiplet（2010s–）

当几何缩放撞上物理墙与经济墙，行业转向"拼装而非缩小"——**More than Moore**。关键技术是
2.5D 封装（TSMC CoWoS）、HBM、Chiplet（AMD）、以及 3D 混合键合堆叠（TSMC SoIC、Intel
Foveros、AMD 3D V-Cache、Apple UltraFusion）。这是"几何缩放"与"韬定律"之间承上启下的桥。

- [先进封装与Chiplet_超越摩尔_介绍.md](packaging/先进封装与Chiplet_超越摩尔_介绍.md) — 中文介绍

---

## 六、何庭波与"韬定律"（τ 缩放，2026）

2026 年 5 月 25 日，华为董事、半导体业务部（海思）总裁 **何庭波**（Tingbo He）在
IEEE 国际电路与系统研讨会（ISCAS 2026，上海）提出 **"韬定律"（τ 缩放）**：以"时间缩微"
替代"几何缩微"，通过逻辑折叠（LogicFolding）等创新压缩信号传播时延（τ，时间常数），跨越
单芯片几何缩放的物理极限。

### 论文①（理论，开放获取）

- [He_2026_A_time_scaling_theory_for_multi-layer_electronic_systems.pdf](tau/He_2026_A_time_scaling_theory_for_multi-layer_electronic_systems.pdf) — 原文 PDF
  （*Science China Information Sciences*, Vol. 69, No. 8, 183401, 2026；DOI 10.1007/s11432-026-5028-5）
- [He_2026_tau_scaling.txt](tau/He_2026_tau_scaling.txt) — 提取的纯文本
- [He_2026_时间缩微理论_中文.md](tau/He_2026_时间缩微理论_中文.md) — 中文全文翻译

**八章结构**：引言 → 几何时代终结 → 时间而非空间 → 逻辑折叠实证 → AI 数据中心的 τ 缩放
→ 逻辑与存储再融合 → 开放挑战 → 六年回顾十年展望。

### 论文②（散热回应）

- [He_2026_Huawei_tau_chip_melt_arXiv2609.04287.pdf](tau/He_2026_Huawei_tau_chip_melt_arXiv2609.04287.pdf) — 原文 PDF（arXiv:2609.04287, 7 页）
- [He_2026_tau_chip_melt.txt](tau/He_2026_tau_chip_melt.txt) — 提取的纯文本
- [He_2026_τ芯片散热_中文.md](tau/He_2026_τ芯片散热_中文.md) — 中文全文翻译

核心是"通勤"比喻：芯片上真正耗能的是数据移动（通勤）而非计算（办公），逻辑折叠缩短了
"通勤"距离，所以更密的芯片反而更凉。

### 报道

- [WIRED_Huawei_Chip_Queen_2026-05-27.md](tau/WIRED_Huawei_Chip_Queen_2026-05-27.md) — WIRED 报道（Will Knight，英文）
- [中国经济网_韬定律_2026-05-27.md](tau/中国经济网_韬定律_2026-05-27.md) — 中国青年报报道（中文）

---

## 七、延伸思考

- [韬定律与新Mead-Conway革命.md](notes/韬定律与新Mead-Conway革命.md) — 韬定律下，是否会出现新的 Mead–Conway 式设计革命？
- [韬定律缺一个特征时间τ.md](notes/韬定律缺一个特征时间τ.md) — λ 是单一标量，τ 目前是分层向量：时间缩微还缺一个"特征时间"
- [补上时间缩放规则与τ特征量_草案.md](notes/补上时间缩放规则与τ特征量_草案.md) — 尝试补上"τ 版 Dennard"与"τ 版 λ"
- [逻辑折叠的双收益与天花板.md](notes/逻辑折叠的双收益与天花板.md) — 修正：密度线性（摩尔延续）+ 延迟递减（τ 新增），两者天花板不同
- [λ缩放与逻辑折叠_不对称.md](notes/λ缩放与逻辑折叠_不对称.md) — λ 缩放是"换尺度"，逻辑折叠加层是"换结构"

---

## 目录结构

```
.
├── README.md                              # 本文件
├── index.html                             # 主线可视化时间线
├── moore/                                 # 摩尔定律原文 + 文本 + 翻译
├── dennard/                               # Dennard 定律 + 多核转向
├── mead_conway/                           # Mead–Conway 教材 + Carver Mead 介绍 + MPC
│   └── mpc/                               # MPC 历史文献（Lynn Conway 档案）
├── eda/                                   # EDA 介绍
├── packaging/                             # 先进封装 / Chiplet 介绍
├── tau/                                   # 韬定律两篇论文 + 翻译 + 报道
└── notes/                                 # 延伸思考（5 篇思辨）
```
