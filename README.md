# From Moore's to Tau：从摩尔定律到韬定律

一份关于**半导体"缩放定律"演进史**的资料库：从戈登·摩尔 1965 年的预言，到 Dennard
的缩放规则、Mead–Conway 的设计方法革命、EDA 工具，再到 2026 年何庭波提出的"韬定律"（τ 缩放）。

主线逻辑：**每当"空间缩放"走到尽头，人类就转向新的度量——从密度，到设计抽象，再到时间本身。**

---

## 时间线总览

| 年份 | 事件 | 本质 |
|------|------|------|
| 1965 | 摩尔提出密度翻倍预测 | 观察：芯片会变得多快？ |
| 1974 | Dennard 缩放定律 | 物理规则：缩小了功耗怎么办？ |
| 1980 | Mead–Conway VLSI 方法学 | 工程方法：如何设计出越来越复杂的芯片？ |
| 1980s– | EDA 兴起（Synopsys / Cadence） | 工具：把方法学变成软件 |
| 2005 | Dennard 缩放失效 → 多核转向 | "免费午餐"结束，从提频转向堆核 |
| 2010s– | 先进封装 / Chiplet（More than Moore） | 应对：不缩小，改拼装 |
| 2026 | 何庭波提出韬定律（τ 缩放） | 新度量：以"时间"替代"空间" |

---

## 一、摩尔定律（1965）

戈登·摩尔 1965 年 4 月 19 日发表在《Electronics》杂志的论文
《Cramming More Components onto Integrated Circuits》（把更多元件塞进集成电路）。

- [moore_1965.pdf](moore_1965.pdf) — 原始论文 PDF（IEEE 重印版，4 页）
- [moore_1965.txt](moore_1965.txt) — 提取出的纯文本
- [moore_1965_zh.md](moore_1965_zh.md) — 中文全文翻译

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

- [dennard/Dennard_1974_ion-implanted_MOSFET.pdf](dennard/Dennard_1974_ion-implanted_MOSFET.pdf) — 原始论文 PDF（13 页）
- [Dennard_定律介绍.md](Dennard_定律介绍.md) — 中文介绍（缩放规则、免费午餐、失效、与摩尔定律的关系）
- [多核转向_免费午餐的终结_介绍.md](多核转向_免费午餐的终结_介绍.md) — 2005 年 Dennard 失效的直接后果：单核频率撞功耗墙，行业从"提频"转向"堆核"

---

## 三、Carver Mead 与现代 VLSI 设计方法（1980）

"摩尔定律"这一名称正是加州理工教授 **Carver Mead** 命名的。他与 Lynn Conway 合著的
《Introduction to VLSI Systems》（1980）引发了 **Mead–Conway VLSI 设计革命**：把芯片
设计从底层工艺中抽象出来，让普通计算机科学家也能设计大规模芯片——现代芯片设计流程的源头。

- [Carver_Mead_介绍.md](Carver_Mead_介绍.md) — Carver Mead 工作全貌的中文介绍

### λ 设计规则（Mead–Conway 方法学的技术核心）

在 Mead–Conway 之前，设计规则是**绝对尺寸**（每层金属多宽、间距多少，全是具体微米数值，
且每一代工艺都不一样），设计死死绑定工艺、不可移植。Mead–Conway 的革新是：把所有几何
尺寸都表示成**单一参数 λ 的整数倍**（λ = 最小特征尺寸的一半），例如最小线宽 = 2λ、
最小间距 = 3λ、接触孔 = 2λ×2λ。于是：

- 设计**不绑定工艺**：换工艺只需按比例缩放 λ，版图即可移植；
- 规则简单到**可教学**（民主化的关键）；
- 天然支持**等比缩放**（与 Dennard 缩放思想一脉相承）。

EDA 厂商后来把这套 λ 倍率写成了 DRC（设计规则检查）规则库——直到今天仍在用。

### 教材与文献（`mead_conway_vlsi/`）

- [V1.pdf](mead_conway_vlsi/V1.pdf) — 《Introduction to VLSI Systems》第一卷（系统设计）
- [V2.pdf](mead_conway_vlsi/V2.pdf) — 第二卷（电路设计）
- [V3.one-sided.pdf](mead_conway_vlsi/V3.one-sided.pdf) — 第三卷（器件与物理，单面版）
- [The_Design_of_VLSI_Design_Methods.pdf](mead_conway_vlsi/The_Design_of_VLSI_Design_Methods.pdf) — Conway《The Design of VLSI Design Methods》（ESSCIRC 1982）

### MPC：多项目晶圆（"民主化"基石）

Mead–Conway 革命之所以是"革命"而非一家公司的内部成果，关键在于 **MPC（Multi-Project
Chip）**——把多个设计拼到同一片晶圆流片、分摊成本，让大学和学生也负担得起真实流片。

- [MPC_多项目晶圆_介绍.md](MPC_多项目晶圆_介绍.md) — 中文介绍
- [mpc/MIT78.pdf](mpc/MIT78.pdf) — MIT 1978 年 VLSI 课程档案（MPC 源头）
- [mpc/ImpDoc79.pdf](mpc/ImpDoc79.pdf) — MPC79 实施文档
- [mpc/MPC79ChipPhotos.pdf](mpc/MPC79ChipPhotos.pdf) — MPC79 芯片照片
- [mpc/MPCAdv.pdf](mpc/MPCAdv.pdf) — MPC 后续推进文档

> 来源：Lynn Conway 官网免费提供的 VLSI 教材与历史档案，英文原文，未做翻译。

---

## 四、EDA：从方法学到工具（1980s 至今）

Mead–Conway 提供的是**方法学**（抽象、λ 规则、层次化设计），而 **EDA（电子设计自动化）**
把这套方法变成设计师每天使用的软件工具链——逻辑综合、布局布线、仿真验证、物理验证。
没有 EDA，方法学就停留在教科书上；正是 EDA 让"设计芯片"从手工画版图变成可复用、可验证
的软件工程。

核心玩家是 **Synopsys**（1986，逻辑综合起家）、**Cadence**（1988）与 **Siemens EDA
（原 Mentor Graphics）**。其中逻辑综合（RTL → 门级网表自动生成）是 Mead–Conway 层次化
思想在软件上的革命性兑现。

何庭波韬定律论文第 7 章明确点出：现有 EDA 是"为 2D 平面时代开发的"，无法适配逻辑折叠
的 3D 堆叠，需要"τ 原生、3D 原生"的下一代工具链——这正是 τ 时代最关键的空白。

- [EDA_电子设计自动化_介绍.md](EDA_电子设计自动化_介绍.md) — EDA 的中文介绍

---

## 五、先进封装与 Chiplet：超越摩尔（2010s–）

当几何缩放撞上物理墙与经济墙，行业转向"拼装而非缩小"——**More than Moore**。关键技术是
2.5D 封装（TSMC CoWoS）、HBM、Chiplet（AMD）、以及 3D 混合键合堆叠（TSMC SoIC、Intel
Foveros、AMD 3D V-Cache、Apple UltraFusion）。

这是"几何缩放"与"韬定律"之间承上启下的桥：向下承接 Dennard 失效后行业实际走的路，向上
引出韬定律——逻辑折叠本质上是把这波"芯片级堆叠"激进地推进到"电路级、单元级"的垂直折叠。

- [先进封装与Chiplet_超越摩尔_介绍.md](先进封装与Chiplet_超越摩尔_介绍.md) — 中文介绍

---

## 六、何庭波与"韬定律"（τ 定律 / Tau Scaling Law，2026）

2026 年 5 月 25 日，华为董事、半导体业务部（海思）总裁 **何庭波**（Tingbo He）在
IEEE 国际电路与系统研讨会（ISCAS 2026，上海）提出 **"韬定律"（τ 缩放）**：主张以
"时间缩微"替代"几何缩微"，通过逻辑折叠（LogicFolding）等创新压缩信号传播时延（τ，
时间常数），跨越单芯片几何缩放的物理极限。

### 论文①（理论，开放获取）

- [He_2026_A_time_scaling_theory_for_multi-layer_electronic_systems.pdf](tau_law/He_2026_A_time_scaling_theory_for_multi-layer_electronic_systems.pdf) — 原文 PDF
  （*Science China Information Sciences*, Vol. 69, No. 8, 183401, 2026；DOI 10.1007/s11432-026-5028-5）
- [He_2026_tau_scaling.txt](tau_law/He_2026_tau_scaling.txt) — 提取的纯文本
- [He_2026_时间缩微理论_中文.md](tau_law/He_2026_时间缩微理论_中文.md) — 中文全文翻译

**八章结构**：引言 → 几何时代终结 → 时间而非空间 → 逻辑折叠实证 → AI 数据中心的 τ 缩放
→ 逻辑与存储再融合 → 开放挑战 → 六年回顾十年展望。

### 论文②（散热回应）

- [He_2026_Huawei_tau_chip_melt_arXiv2609.04287.pdf](tau_law/He_2026_Huawei_tau_chip_melt_arXiv2609.04287.pdf) — 原文 PDF（arXiv:2609.04287, 7 页）
- [He_2026_tau_chip_melt.txt](tau_law/He_2026_tau_chip_melt.txt) — 提取的纯文本
- [He_2026_τ芯片散热_中文.md](tau_law/He_2026_τ芯片散热_中文.md) — 中文全文翻译

核心是"通勤"比喻：芯片上真正耗能的是数据移动（通勤）而非计算（办公），逻辑折叠缩短了
"通勤"距离，所以更密的芯片反而更凉。

### 报道

- [WIRED_Huawei_Chip_Queen_2026-05-27.md](tau_law/WIRED_Huawei_Chip_Queen_2026-05-27.md) — WIRED 报道（Will Knight，英文）
- [中国经济网_韬定律_2026-05-27.md](tau_law/中国经济网_韬定律_2026-05-27.md) — 中国青年报报道（中文）

---

## 七、延伸思考

- [韬定律与新Mead-Conway革命.md](韬定律与新Mead-Conway革命.md) — 韬定律下，是否会出现新的 Mead–Conway 式设计革命？
  结论：技术前提已具备，但"开放、教学、可复制"的社会前提尚未出现。
- [韬定律缺一个特征时间τ.md](韬定律缺一个特征时间τ.md) — 一次诚恳的探讨：λ 是单一物理标量
  （有 Dennard 兜底），而 τ 目前更像跨 12 个数量级的分层向量——"时间缩微"还需要一个可操作的
  "特征时间 τ"和一条"τ 版 Dennard 定律"；但也坦诚：这可能只是"时间还没到"，正如摩尔定律
  也等了 9 到 15 年。
- [补上时间缩放规则与τ特征量_草案.md](补上时间缩放规则与τ特征量_草案.md) — 尝试补上韬定律缺的两块：
  "τ 版 Dennard"（距离–延迟平方律 τ∝L²、时间–能量耦合律、EDP 三次方不变量）与"τ 版 λ"
  （单位长度延迟常数 τ₀）。思辨性草案，未经验证。

---

## 目录结构

```
.
├── README.md                              # 本文件
├── moore_1965.pdf / .txt / _zh.md         # 摩尔定律原文 + 文本 + 中文翻译
├── Dennard_定律介绍.md                     # Dennard 定律中文介绍
├── 多核转向_免费午餐的终结_介绍.md          # 2005 多核转向中文介绍
├── dennard/Dennard_1974_....pdf           # Dennard 1974 原始论文
├── Carver_Mead_介绍.md                     # Carver Mead 工作中文介绍
├── mead_conway_vlsi/                       # Mead–Conway VLSI 教材与论文
├── MPC_多项目晶圆_介绍.md                  # MPC 中文介绍
├── mpc/                                    # MPC 历史文献（Lynn Conway 档案）
├── EDA_电子设计自动化_介绍.md               # EDA 中文介绍
├── 先进封装与Chiplet_超越摩尔_介绍.md         # 先进封装/More than Moore 中文介绍
├── 韬定律与新Mead-Conway革命.md             # 延伸思考
├── 韬定律缺一个特征时间τ.md                  # 延伸思考（技术软肋）
├── 补上时间缩放规则与τ特征量_草案.md          # 延伸思考（尝试补缺）
└── tau_law/                                # 何庭波韬定律两篇论文 + 翻译 + 报道
```
