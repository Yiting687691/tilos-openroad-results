# TILOS MacroPlacement · 基线结果

[数据来源](https://github.com/TILOS-AI-Institute/MacroPlacement) · [配套候选](https://github.com/Yiting687691/tilos-openroad-optimized-results)。单位：线长 µm，时序 ns；— 为待补结果。

## 结果

| 设计 | 小循环 HPWL | 小循环 WNS / TNS | OpenROAD RWL | OpenROAD WNS / TNS | 状态 |
|---|---:|---:|---:|---:|---|
| MemPool tile | — | — | — | — | 待补当前版本结果 |
| NVDLA partition-c | — | — | — | — | 待适配及配对基线 |

仅采用同输入、同后端配置的配对结果；宏位置/朝向可变，标准单元由 OpenROAD 重摆。完整布线后报告 WNS/TNS、线长收益及 DRC；不把预布局改善当作布线收益。
优先 MemPool tile；NVDLA 的上游 OpenROAD 流程未现成验证，需要适配后再测。
