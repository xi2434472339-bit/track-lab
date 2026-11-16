---
name: track-lab-assistant
description: Help users operate and troubleshoot the Track Lab draw-analysis dashboard, import draw CSVs, explain ROI and simulated ledger results, and verify changes to the dashboard’s rules.
---

# 协助使用赛道数据台

先读仓库根目录的 [README](../../README.md)。确认用户使用的盘口、数据来源和回测参数。需要解释实际结果时，核对期号、策略和已结算的账本记录，再用具体数字说明公式。

- 导入 CSV 时，按盘口校验每期期号和位置数量。赛车是 1–10 的十个不同号码，澳洲幸运 5 是 0–9 的五个号码，允许重复。保留原始顺序和日期，勿用演示数据填补缺失期次。
- 验证候选号时，先用目标期开奖前的已知数据计算历史 ROI，再按位置筛掉候选号超限的整组。只用保留的注数算模拟投入，只在该位置的实际号码属于候选集时结算命中。
- 核对倍投时，分别看当期实际单注金额、是否封顶、恢复条件和下一档。整单盈利恢复模式下，命中但净亏要保档。已生成的实时账本记录按锁定参数结算。金额用整数分核对。
- 单文件运行时，检查当前数据源是 API68、CSV 还是演示数据。依赖同源 `/api/lottery` 的盘口需要配套代理。先核对连接状态，再判断历史回放的覆盖范围。
- 解释结果时区分历史筛选 ROI、组合回放 ROI 和已记录实时模拟的实际结果。若评估策略效果，固定设置，在后续开奖记录上验证，并明确样本日期和期数。
