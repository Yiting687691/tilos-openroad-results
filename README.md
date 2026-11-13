# TILOS MacroPlacement · 基线与文献参照

[配套仓库](https://github.com/Yiting687691/tilos-openroad-optimized-results) · [文献参照](https://github.com/Yiting687691/tilos-openroad-results/blob/main/BEST_REPORTED.md)

## 按指标选择文献参照

| 设计 / 文献配置 | 最短 RWL | 最好 WNS | 最好 TNS |
|---|---:|---:|---:|
| MemPool tile / ASAP7¹ | DREAMPlace 4.0 | DP4＋IncreMacro 2025 | DP4＋IncreMacro 2025 |
| NVDLA / ASAP7¹ | DP4＋IncreMacro 2025 | 三方法并列 | 三方法并列 |
| NVDLA / NG45² | AutoDMP macro-only | Innovus sequential | Innovus sequential |

¹ IncreMacro Table V；² AutoDMP Table 2。均为对应原表内最优；当前本地输入尚未与这些版本逐项匹配。[数值、收益与其他配置](BEST_REPORTED.md)。

## 已有实测基线

线长单位 mm，时序单位 ns；— 为未发布。

| 设计 | 布局来源 | HPWL / mm | RWL / mm | WNS | TNS |
|---|---:|---:|---:|---:|---:|
| MemPool tile | 待核验布局来源 | — | — | — | — |
| NVDLA partition-c | 待核验布局来源 | — | — | — | — |

NVDLA partition-c 仍需本地 OpenROAD 适配；不将其他 ORFS 同名变体的结果直接填入。
