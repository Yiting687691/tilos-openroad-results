# TILOS MacroPlacement · 基线与文献参照

[全部方法调研](https://github.com/Yiting687691/open-source-openroad-results/blob/main/METHODS.md) · [作者布局与复测入口](https://github.com/Yiting687691/open-source-openroad-results/blob/main/ARTIFACTS.md)

[配套仓库](https://github.com/Yiting687691/tilos-openroad-optimized-results) · [文献参照](https://github.com/Yiting687691/tilos-openroad-results/blob/main/BEST_REPORTED.md)

## 按指标选择文献参照

<table>
<thead><tr><th>设⁠计⁠ ⁠/⁠ ⁠文⁠献⁠配⁠置</th><th>最⁠短⁠ ⁠R⁠W⁠L</th><th>最⁠好⁠ ⁠W⁠N⁠S</th><th>最⁠好⁠ ⁠T⁠N⁠S</th></tr></thead>
<tbody>
<tr><td>M⁠e⁠m⁠P⁠o⁠o⁠l⁠ ⁠t⁠i⁠l⁠e⁠ ⁠/⁠ ⁠A⁠S⁠A⁠P⁠7⁠¹</td><td align="right">D⁠R⁠E⁠A⁠M⁠P⁠l⁠a⁠c⁠e⁠ ⁠4⁠.⁠0</td><td align="right">D⁠P⁠4⁠＋⁠I⁠n⁠c⁠r⁠e⁠M⁠a⁠c⁠r⁠o⁠ ⁠2⁠0⁠2⁠5</td><td align="right">D⁠P⁠4⁠＋⁠I⁠n⁠c⁠r⁠e⁠M⁠a⁠c⁠r⁠o⁠ ⁠2⁠0⁠2⁠5</td></tr>
<tr><td>N⁠V⁠D⁠L⁠A⁠ ⁠/⁠ ⁠A⁠S⁠A⁠P⁠7⁠¹</td><td align="right">D⁠P⁠4⁠＋⁠I⁠n⁠c⁠r⁠e⁠M⁠a⁠c⁠r⁠o⁠ ⁠2⁠0⁠2⁠5</td><td align="right">三⁠方⁠法⁠并⁠列</td><td align="right">三⁠方⁠法⁠并⁠列</td></tr>
<tr><td>N⁠V⁠D⁠L⁠A⁠ ⁠/⁠ ⁠N⁠G⁠4⁠5⁠²</td><td align="right">A⁠u⁠t⁠o⁠D⁠M⁠P⁠ ⁠m⁠a⁠c⁠r⁠o⁠-⁠o⁠n⁠l⁠y</td><td align="right">I⁠n⁠n⁠o⁠v⁠u⁠s⁠ ⁠s⁠e⁠q⁠u⁠e⁠n⁠t⁠i⁠a⁠l</td><td align="right">I⁠n⁠n⁠o⁠v⁠u⁠s⁠ ⁠s⁠e⁠q⁠u⁠e⁠n⁠t⁠i⁠a⁠l</td></tr>
</tbody>
</table>

¹ IncreMacro Table V；² AutoDMP Table 2。均为对应原表内最优；当前本地输入尚未与这些版本逐项匹配。[数值、收益与其他配置](BEST_REPORTED.md)。

## 已有实测基线

线长单位 mm，时序单位 ns；— 为未发布。

<table>
<thead><tr><th>设⁠计</th><th>布⁠局⁠来⁠源</th><th>H⁠P⁠W⁠L⁠ ⁠/⁠ ⁠m⁠m</th><th>R⁠W⁠L⁠ ⁠/⁠ ⁠m⁠m</th><th>W⁠N⁠S</th><th>T⁠N⁠S</th></tr></thead>
<tbody>
<tr><td>M⁠e⁠m⁠P⁠o⁠o⁠l⁠ ⁠t⁠i⁠l⁠e</td><td align="right">待⁠核⁠验⁠布⁠局⁠来⁠源</td><td align="right">—</td><td align="right">—</td><td align="right">—</td><td align="right">—</td></tr>
<tr><td>N⁠V⁠D⁠L⁠A⁠ ⁠p⁠a⁠r⁠t⁠i⁠t⁠i⁠o⁠n⁠-⁠c</td><td align="right">待⁠核⁠验⁠布⁠局⁠来⁠源</td><td align="right">—</td><td align="right">—</td><td align="right">—</td><td align="right">—</td></tr>
</tbody>
</table>

NVDLA partition-c 仍需本地 OpenROAD 适配；不将其他 ORFS 同名变体的结果直接填入。
