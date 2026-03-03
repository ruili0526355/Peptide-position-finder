# Peptide Position Finder

一个用于定位肽段中氨基酸在蛋白全长序列中精确位置的网页工具。

**peptide_position_finder.html** 是一个完整的单页网页工具，下载后用浏览器打开即可，**无需网络、无需安装**。

## 在线访问
https://github.com/ruili0526355/Peptide-position-finder/

---

## 使用方法

1. 上传 FASTA 文件 → 拖拽或点击上传你的蛋白质序列文件
2. 上传 peptide.tsv 文件 → 上传你的搜索结果表格
3. 输入肽段序列，例如 `SKDYEFMWNPHLGYILTCPSNLGTGLR`
4. 输入目标氨基酸，例如 `C`
5. 点击 🔍 查询 或按 Enter

---

## 输出结果包括

| 模块 | 内容 |
|------|------|
| **概览统计** | 肽段长度、在蛋白中的起止位置、目标AA出现次数 |
| **蛋白全长可视化** | 高亮肽段区域（黄色）和目标AA位置（蓝/红），悬停显示精确位置 |
| **位置列表表格** | 每个目标AA在蛋白全长中的位置、肽段内位置、±3个上下文 |
| **TSV匹配信息** | 从你的搜索结果中提取该肽段的修饰、Intensity等信息 |

---

## 定位逻辑

- 优先从 TSV 的 `Entry Name` 和 `Protein Start` 字段获取位置信息
- 若 TSV 无记录，则在 FASTA 中直接字符串搜索该肽段
- 最终报告目标氨基酸在**蛋白全长**中的绝对位置（1-based）


