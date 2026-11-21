# 摩尔定律（Moore's Law）相关资料

## 原文出处

摩尔定律的"原文"是戈登·摩尔（Gordon E. Moore）1965 年 4 月 19 日发表在行业杂志
《Electronics》（第 114–117 页）上的论文：

> **Cramming More Components onto Integrated Circuits**
> （把更多元件塞进集成电路）

本目录已下载该论文的全文（IEEE 1998 年重印版，含图注）与提取出的纯文本：

- `moore_1965.pdf` — 论文扫描/重印版 PDF
- `moore_1965.txt` — 提取出的纯文本（可全文搜索）

## 关键原文摘录

关于翻倍速率的预测（论文第四节 "COSTS AND CURVES"）：

> "The complexity for minimum component costs has increased at a rate of
> roughly a factor of two per year... Certainly over the short term this rate
> can be expected to continue, if not to increase. Over the longer term, the
> rate of increase is a bit more uncertain, although there is no reason to
> believe it will not remain nearly constant for at least 10 years. That means
> by 1975, the number of components per integrated circuit for minimum cost
> will be 65,000."
>
> （最低成本的复杂度大约以每年翻一番的速率增长……短期内这一速率将持续甚至加快；
> 长期看虽有不确定性，但没有理由认为它不会在至少 10 年内保持恒定。这意味着到 1975 年，
> 每个集成电路最低成本下的元件数将达到 6.5 万个。）

关于应用前景的预言（论文开头）：

> "Integrated circuits will lead to such wonders as home computers—or at least
> terminals connected to a central computer—automatic controls for automobiles,
> and personal portable communications equipment."
>
> （集成电路将带来家用计算机——或至少是连接到中央计算机的终端——汽车自动控制、
> 以及个人便携式通信设备等奇迹。）

## 常见误解澄清

1. **摩尔本人当年并未使用"摩尔定律"（Moore's Law）这个词**。该名称是
   加州理工教授 Carver Mead 在 1970 年代后期命名的。
2. **原始预测是"每年翻番"**（1965 年）。1975 年摩尔在第二篇论文中将其修正为
   "每两年翻一番"。
3. 摩尔说的是"元件数（components）"，不是狭义的"晶体管数"，虽然实践中常以
   晶体管数衡量。

## 摩尔 1975 年修正论文

- 标题：**Progress in Digital Integrated Electronics**（数字集成电路的进展）
- 出处：1975 年 IEEE 国际电子器件会议（IEDM）技术文摘，第 11–13 页
- DOI：10.1109/IEDM.1975.188490（IEEE Xplore，付费）
- 内容：将翻倍周期从 1 年修正为约 2 年，并分析了促成该趋势的技术经济因素。

## 参考链接

- 原始论文 PDF（UT Austin 课程镜像）：https://www.cs.utexas.edu/~fussell/courses/cs352h/papers/moore.pdf
- Intel 官方"摩尔定律"博物馆页：https://www.intel.com/content/www/us/en/history/museum-gordon-moore-law.html
- 1975 年论文（IEEE Xplore）：https://doi.org/10.1109/IEDM.1975.188490

## Carver Mead 与现代 VLSI 设计方法

"摩尔定律"这一名称正是加州理工教授 **Carver Mead** 命名的。他同时也是**现代集成电路
（VLSI）设计方法学**的奠基人，与 Lynn Conway 合著的《Introduction to VLSI Systems》
（1980，Addison-Wesley）一书引发了著名的 "Mead–Conway VLSI 设计革命"。

该书把芯片设计从底层制造工艺中抽象出来，建立了可扩展的设计规则（λ 规则）、层次化
设计、结构化设计与时序设计等方法，使得普通计算机科学家（而不仅是器件物理学家）也能
设计大规模芯片——这正是今天所有现代芯片设计流程的源头。

已下载的资料位于 `mead_conway_vlsi/` 目录：

- `V1.pdf` — 第一卷（系统设计）
- `V2.pdf` — 第二卷（电路设计）
- `V3.one-sided.pdf` — 第三卷（器件与物理，单面版）
- `The_Design_of_VLSI_Design_Methods.pdf` — Lynn Conway 论文《The Design of VLSI
  Design Methods》（ESSCIRC 1982，讲述 VLSI 设计方法本身的设计）

> 来源：Lynn Conway 官网免费提供的 VLSI 教材与文献镜像。
> 说明：以上为 Mead & Conway 三卷本全书的扫描/重排版，英文原文，未做翻译。

## 何庭波与"韬定律"（τ 定律 / Tau Scaling Law）

2026 年 5 月 25 日，华为董事、半导体业务部（海思）总裁 **何庭波**（Tingbo He）在
IEEE 国际电路与系统研讨会（ISCAS 2026，上海）提出 **"韬定律"（τ 定律，Tau Scaling Law）**，
主张以"时间缩微"替代"几何缩微"作为半导体演进的新指导原则——通过逻辑折叠（LogicFolding）
等创新，压缩信号传播时延（τ，时间常数），跨越单芯片几何缩放的物理极限。

相关材料位于 `tau_law/` 目录：

- `He_2026_A_time_scaling_theory_for_multi-layer_electronic_systems.pdf` — **何庭波署名论文
  原文 PDF**《A time scaling theory for multi-layer electronic systems》（开放获取，CC BY 4.0）
  - 出处：*Science China Information Sciences*, Vol. 69, No. 8, 183401 (2026)
  - DOI：https://doi.org/10.1007/s11432-026-5028-5
- `He_2026_tau_scaling.txt` — 上述论文提取出的纯文本（可全文搜索）
- `He_2026_Huawei_tau_chip_melt_arXiv2609.04287.pdf` — **何庭波第二篇论文 PDF**
  《Huawei's τ Chip Was Supposed to Melt?》（7 页，2 图，8 参考文献）
  - 出处：arXiv:2609.04287 (cs.AR)，提交于 2026-09-03
  - 主题：回应 τ 缩放定律最尖锐的质疑——**散热（热问题）**；用麒麟实测数据论证
    "芯片上真正消耗能量的是数据移动（通勤），而非计算本身（办公）"
- `He_2026_tau_chip_melt.txt` — 上述第二篇论文提取出的纯文本
- `WIRED_Huawei_Chip_Queen_2026-05-27.md` — WIRED 报道《Huawei's 'Chip Queen' Throws
  Down the Gauntlet》（Will Knight，2026-05-27，英文全文）
- `中国经济网_韬定律_2026-05-27.md` — 中国青年报《"韬定律"：在时间的缝隙里突围》（中文全文）

论文核心内容（8 章）：

1. Introduction — 引言
2. The end of the geometric era — 几何缩微时代的终结
3. Time, not space: the real currency of Moore's era — 时间而非空间，才是摩尔时代真正的"货币"
4. LogicFolding: a mobile-SoC proof point — 逻辑折叠：移动 SoC 的实证（55% 密度提升、41% 功耗降低）
5. From picoseconds to microseconds: τ scaling in the AI data center — 从皮秒到微秒：AI 数据中心的 τ 缩放
6. Logic and memory: from decoupling to re-fusion — 逻辑与存储：从解耦到再融合
7. Open challenges — 开放挑战
8. Six years in, ten years out — 六年回顾、十年展望
