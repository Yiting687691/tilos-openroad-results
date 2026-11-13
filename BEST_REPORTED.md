# TILOS · 分配置文献参照

各指标允许不同算法；同一设计名的工艺、频率和网表变体分别列出。表内最优不代表全领域最优，未作为本项目实测分母。

## 两例紧凑的逐指标对标方法表

这里的“最佳”均限定在指定来源表和配置内。

| 设计 / 配置 | 最短 RWL：算法 / µm | 最好 WNS：算法 / ns | 最好 TNS：算法 / ns | 来源 |
|---|---|---|---|---|
| MemPool tile，ASAP7，IncreMacro Table V | DREAMPlace 4.0 / 787,043 | DP4 + IncreMacro 2025 / 0 | DP4 + IncreMacro 2025 / 0 | S1 |
| NVDLA，ASAP7，IncreMacro Table V | DP4 + IncreMacro 2025 / 2,225,188 | 3 方法并列 / 0 | 3 方法并列 / 0 | S1 |
| MemPool，ASAP7，20 宏 / 131,732 实例，333 MHz | MacroAgent / 752,503 | MacroAgent / −0.369 | MacroAgent / −1,048.010 | S2 Table 6 |
| NVDLA，NG45，128 宏 / 153,561 实例，500 MHz | MacroAgent / 8,806,758 | MacroAgent / −0.021 | MacroAgent / −0.129 | S2 Table 6 |
| NVDLA，NG45，128 宏 / 约 145k cell，1,111 MHz | AutoDMP macro-only / 8,560,000 | Innovus sequential mixed-size / −0.004 | Innovus sequential mixed-size / −0.043 | S3 Table 2 |

S1 的 NVDLA 时序并列方法为 DP4 + MP-tree、DP4 + IncreMacro 2024、DP4 + IncreMacro 2025。S2 Table 7 另有不同流程的 MacroAgent + Innovus：MemPool RWL 810,131 µm，NVDLA RWL 8,033,640 µm；该表没有 WNS/TNS，不能拼接 Table 6 的时序构造虚拟最优布局。

## 原始数值与收益分开

收益按 WL=(基线−候选)/基线，WNS/TNS=(候选−基线)/|基线|。正为改善，负为劣化；零分母不计算。

| 设计 / 来源 | 算法 | 原比较分母 | RWL 收益 | WNS 收益 | TNS 收益 |
|---|---|---|---:|---:|---:|
| MemPool tile / S1 Table V | IncreMacro 2025 + DP4 | DREAMPlace 4.0 | −4.18% | +100.00% | +100.00% |
| NVDLA ASAP7 / S1 Table V | IncreMacro 2025 + DP4 | DREAMPlace 4.0 | +14.62% | +100.00% | +100.00% |
| MemPool / S2 Table 6 | MacroAgent | DREAMPlace | +3.34% | +6.82% | +13.19% |
| NVDLA NG45 / S2 Table 6 | MacroAgent | DREAMPlace | +0.49% | +89.90% | +94.52% |
| NVDLA NG45 / S3 Table 2 | AutoDMP macro-only | Innovus sequential mixed-size | +3.71% | −50.00% | −6.98% |

### S1：IncreMacro Table V 抽取

| 设计 | 方法 | RWL / µm | WNS / ns | TNS / ns |
|---|---|---:|---:|---:|
| mempool_tile | DREAMPlace 4.0 | 787043 | −0.01 | −0.28 |
| mempool_tile | DP4 + MP-tree | 1103988 | −0.67 | −2991.80 |
| mempool_tile | DP4 + IncreMacro 2024 | 819267 | −0.03 | −8.54 |
| mempool_tile | DP4 + IncreMacro 2025 | 819949 | 0 | 0 |
| nvdla | DREAMPlace 4.0 | 2606292 | −3.08 | −6036.20 |
| nvdla | DP4 + MP-tree | 3209693 | 0 | 0 |
| nvdla | DP4 + IncreMacro 2024 | 2229943 | 0 | 0 |
| nvdla | DP4 + IncreMacro 2025 | 2225188 | 0 | 0 |

S1 为 ASAP7、密度 0.8，固定宏后用 DREAMPlace 4.0 摆 std cell，再由 Innovus 做 placement-opt、CTS、post-CTS opt、signal route、post-route opt。已直接渲染并核对 AutoDMP 系列 Table III（PDF 第 10 页、印刷页 3231）：该表只有 7 个 Chipyard 设计行，不含 MemPool tile、NVDLA 或其他 TILOS 设计。因此 Table V 已覆盖这篇论文给当前两例提供的全部逐方法 post-route 行，没有漏取 Table III 更优结果。Table III 原页证据保存在同目录 `incremacro_table_III.png`。

## 不能错接到当前两例的相关论文

| 方法 / 来源 | 核查结果 |
|---|---|
| DG-RePlAce / S4 | Table VI 是 MemPool Group（326 宏 / 2529k 实例），不是 MemPool tile；不能移用其收益到 20 宏 tile |
| AutoDMP / S3 | MemPool Group 为 320 宏 / 2.7M cell；另有 ASAP7 NVDLA，不能与 NG45 值混用 |
| Re²MaP / S5 | 已核实 Table II 没有当前 MemPool tile、NVDLA partition-c 或 HighTide 三例的逐例结果 |
| C3PO / S6 | ASAP7 MemPool，162k cell / 20 宏；RWL 1,400,162→1,346,411（+3.84%），WNS −1.193→−1.191（+0.17%），TNS −12.2k→−12.4k（约 −1.64%）。版本/规模不同，不替换上表；TNS 分母取自已舍入原表 |

## 一手来源

- S1：[IncreMacro，TCAD 2025，Table V](https://www.cse.cuhk.edu.hk/~byu/papers/J137-TCAD2025-IncreMacro.pdf)，[DOI](https://doi.org/10.1109/TCAD.2025.3531776)。
- S2：[MacroAgent，2026，Table 1/6/7](https://arxiv.org/html/2608.24946v1)。Table 6 是完整 Innovus P&R，Table 7 是另一套工业后端对照；不是把其快速评估表当布线结果。
- S3：[AutoDMP，2023，Table 2](https://d1qx31qr3h6wln.cloudfront.net/publications/AutoDMP.pdf)。Cadence Innovus 21.15 post-route optimization；本表使用 macro-only handoff 行。
- S4：[DG-RePlAce，2024，Table VI](https://arxiv.org/html/2404.13049v1)。
- S5：[Re²MaP，2025，Table II](https://arxiv.org/html/2511.08054v1)。
- S6：[C3PO，ASPDAC 2026，Table III](https://hhsiao30.github.io/papers/yichen_apsdac26__Camera_Ready_eXpress.pdf)。
- HighTide：[作者仓库](https://github.com/VLSIDA/HighTide)、[论文](https://arxiv.org/html/2606.04126v1)。发布设计 Fmax 不是相对其他布局算法的改善率。

缺口：尚未取得上述论文最佳布局的逐 SHA 输入、布局工件与本地同协议重跑；HighTide 三例暂无已核实独立逐例冠军。这些缺口应留空或写未核实，不自动填写 Hier-RTLMP。
