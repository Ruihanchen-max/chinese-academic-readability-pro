# 中文学术可读性 Pro

**Chinese Academic Readability Pro · v1.9.3**

面向中文学术论文和博士开题报告的 Agent Skill。它帮助作者理清研究问题、证据与推论之间的关系，让读者能准确理解文章主张及其适用范围。适用于运动干预、健康心理学与行为科学等研究，尤其适合处理引言论证跳跃、开题方法细节过密、讨论罗列文献、段落过碎等问题。

**[下载 v1.9.3 完整安装包（ZIP）](https://github.com/Ruihanchen-max/chinese-academic-readability-pro/raw/refs/heads/main/Chinese_Academic_Readability_Pro_v1.9.3.zip)**

## 能做什么

| 你的任务 | 模式 | 可以得到什么 |
| --- | --- | --- |
| 想知道稿件哪里难读 | `diagnose` | 定位问题段落，指出证据缺口、推理断点和修改优先级。原文保持原样。 |
| 想精修表达或重组章节 | `polish` / `rebuild` | 精修只改有必要的句子。重构可调整段落顺序和论证结构，保留事实、数据、引文和推断边界。 |
| 开题报告写得像实施手册 | `depth-control` | 把方法信息分为必写、简述、可省，保留理解研究问题与核心比较所需的设计信息。 |
| 讨论浅、段落碎或读者找不到重点 | `intellectual-depth` / `paragraph-flow` / `reader-navigation` | 深入少数关键论点，检查竞争性解释，按论证任务组织自然段，让研究问题、假设和主要结局更容易找到。 |
| 需要科研示意图或数据图 | `scientific-figures` | 先核对图要回答的问题和证据来源。有明确条件的示意图可交付可编辑 PPTX 和矢量 SVG。数据图使用真实数据与可复现绘图脚本。 |
| 提交前检查 Word 或 PDF | `artifact-qa` | 检查中文缺字、字体、表格、公式、目录页码和最终页面显示，标明通过、失败或未核实。 |
| 想比较不同编辑方案的效果 | `evaluate` | 生成匿名同稿对照材料，供独立读者盲评。 |

编辑时优先保留作者已经确认的研究对象、数值、变量、比较方向和设计。关联、差异及因果判断的措辞随证据强度调整。证据不足的地方会标出，便于作者复核。

## 安装与调用

1. 下载并解压 ZIP，找到整个 `chinese-academic-readability/` 目录。该目录包含 `SKILL.md`，以及配套规则、示例和脚本。
2. 按下表把**整个目录**放进客户端的个人技能目录。同名旧版可先备份。
3. 开启新会话，明确要求使用 `chinese-academic-readability`。若需确认加载版本，让 Agent 检查 `SKILL.md` 中的 `metadata.version` 是否为 `1.9.3`。

| 客户端 | 安装后的目录 |
| --- | --- |
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/chinese-academic-readability/` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/chinese-academic-readability/` |
| [Google Antigravity App](https://antigravity.google/docs/skills) | `~/.gemini/config/skills/chinese-academic-readability/` |

文字诊断与编辑可直接使用 Skill 指令。运行辅助脚本需要 Python 3.10+。Word/PDF 检查还需要相应的 Python 依赖和可用的文档渲染工具，具体配置见安装包内的 `INSTALL_USAGE_CN.md`。

## 可直接复制的用法

**博士课程初步开题**

> 使用 `chinese-academic-readability` 的 `depth-control` 和 `paragraph-flow` 模式审查我提供的开题稿。梳理研究问题、核心比较与主要结局，按必写、简述、可省调整方法细节。保留研究对象、变量、设计、引文及必要的因果与统计限定。给出修改稿和关键改动说明。

**只诊断引言或讨论**

> 使用 `chinese-academic-readability` 的 `diagnose` 模式，标出最影响读者理解的三处段落，说明主张、证据或推理缺在哪里，并给出修改方向。请保持原文。

**科研示意图**

> 使用 `chinese-academic-readability` 的 `scientific-figures` 模式，依据我提供的方案画一张方法示意图。先核对图要解释的变量、规则和情境条件，再交付可编辑 PPTX 和 SVG。图中保留必要标签，图注说明数据来源和适用条件。

**终稿核查**

> 使用 `chinese-academic-readability` 的 `artifact-qa` 模式，对照最终 DOCX 和 PDF，逐页核查中文显示、图表、公式、目录页码及字体。逐项标为 `PASS`、`FAIL` 或 `UNVERIFIED`，附具体页码。

## v1.9.3 更新

- 按每段承担的论证任务调整段落和小标题，让开题与讨论部分保持连贯。
- 增加可编辑的科研时间线示例，演示在给定日程下，几种通知策略会怎样选择步行时间。该图演示策略规则，实际效果仍由研究数据检验。
- 安装包附规则测试、文件校验清单与验证报告。论文可读性的改善幅度仍需通过独立读者评估。

## 安装包内容与许可证

| 文件或目录 | 内容 |
| --- | --- |
| `SKILL.md` | Agent 入口、工作模式及编辑规则 |
| `INSTALL_USAGE_CN.md`、`USAGE_GUIDE_CN.md` | 中文安装说明与使用指南 |
| `references/`、`examples/`、`assets/` | 学术写作规则、案例及可编辑图例 |
| `scripts/`、`tests/`、`evals/` | 辅助检查脚本、回归测试与评测方案 |
| `CHANGELOG.md`、`VALIDATION_REPORT.md` | 版本记录与工程验证范围 |
| `FILES_SHA256.txt`、`LICENSE` | 包内文件校验清单与 MIT 许可全文 |
