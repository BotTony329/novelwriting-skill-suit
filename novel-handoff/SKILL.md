---
name: novel-handoff
description: 长篇连载的交接记录协议（handoff），防止跨会话、跨模型、多人协作写作时的设定漂移与上下文断裂。当用户说"继续写上一章""接着写""换会话/换工具继续写"、需要中断或恢复长篇小说写作，或要审计一部已有手稿的连续性时使用。核心机制：NOVEL_HANDOFF.md 作为项目状态文件，写前必读、写后必更；附风格DNA提取、连续性六类故障审计、跨AI工具移植协议。
---

# Novel Handoff · 交接记录协议

多人/多 AI 接力写同一部长篇小说。后续写作者对本会话毫无记忆——共享文件 `NOVEL_HANDOFF.md` 承载故事状态。**写前不读它不许动笔，写后不更它不许收工。**

## 核心流程（每次会话）

### 1. 写前：定向（Orient）
先读 `NOVEL_HANDOFF.md`，再读最近章节，然后是大纲与设定文档。动笔前用几句话向用户陈述：故事进行到哪儿（卷/章/场景/故事内时间/地点）、下一个 POV 是谁、该角色**知道什么、不知道什么**、哪些线索还开着、推进大纲的哪个 beat、稿件已建立的文风惯例。禁止只从上一段话直接续写。

### 2. 写中：保住这本书的指纹
稿件的实际写法高于任何风格标签。若笔记说"抒情"但正文短促克制，就写短促克制，并在 handoff 记录该分歧。写对话与内心戏前必查 Knowledge Matrix：**任何角色不得知道、暗示或依据未曾获知的信息行动**，哪怕读者知道。注意推理链：如果你埋的线索会让角色在本场景内推出禁忌事实，等于已经揭示——要么削减线索，要么明说这次揭示是主动花掉的。

### 3. 写后：更新 NOVEL_HANDOFF.md（每次，强制）
任何场景、半章、重写、新人物、新设定之后都要更新。**未知信息写 `UNKNOWN`，禁止猜测编造。**

## 深度参考（按需读取）

- **状态文件怎么更新不臃肿**：[references/update-rules.md](references/update-rules.md)——"文件描述现在 + 写未来所需的最少历史"；各节的就地更新/合并/压缩规则
- **风格DNA怎么提取**：[references/style-dna.md](references/style-dna.md)——形容词不可移植，行为才可移植；句节奏/段落密度/对话比/感官习惯/情绪表达方式的度量方法
- **审计已有手稿的连续性**：[references/continuity-audit.md](references/continuity-audit.md)——六类故障：知识泄漏、时间线断裂、物品/身体状态漂移、人设矛盾、世界规则违反、声音漂移。审计只出 findings 清单，不动正文，除非用户要求

## 资产模板

- [assets/NOVEL_HANDOFF_TEMPLATE.md](assets/NOVEL_HANDOFF_TEMPLATE.md)——状态文件完整模板：Project Snapshot / Style DNA / Story So Far（发生的事实 vs 角色认知 vs 仅读者知道）/ Character State / Knowledge Matrix / 伏笔与线索 / Canon Changes
- [assets/PORTABLE_PROTOCOL.md](assets/PORTABLE_PROTOCOL.md)——可移植协议文本：粘贴到任何 AI 写作工具（连同 NOVEL_HANDOFF.md 与稿件），让所有工具遵循同一套系统

## 与其他 skill 的分工

novel-outline 管立项，novel-writing 管单章流程与反重复，novel-proofreading 管写后审校，novel-pacing 管节奏密度。本 skill 管**跨会话/跨写作者的状态连续性**；handoff 与 outline 冲突时以 outline 为准，当场修正 handoff。
