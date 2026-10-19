# novel-to-short-drama · 小说 → AI 短剧七步流水线技能

把小说/网文片段，按**七步死闸门**流程做成 AI 生成的竖屏/横屏短剧（短剧、漫剧、推文剧）。
这是一个给 AI Agent 用的「技能包」：一份编排配方 `SKILL.md` + 每一步的模板和检查清单。全部来自真实项目里反复踩坑后定下的规矩。

> 工具无关：出图、出视频可以用任何画布或 API。文中以 LibTV 画布 + Seedance 2.0 图生视频为例，具体参数写进你自己项目的 `STYLE-LOCK.md`。

## 七步（上一步正式通过，才能开下一步）

1. **改编**：原著 → 改编工作包。情节锁最高优先，事件、时间线、线索、动机、结局零偏差。
2. **独立验收**：另起一个验收官，100 分制，**≥95 且无硬否决且每项达最低线**才算【正式验收通过】。没有「基本通过」。
3. **压节奏**：按短视频平台节奏「行动→阻碍→再行动」，删无关闪回；推进剧情的过渡和半拍喘息要留，不过度压缩。
4. **Clip 分镜**：每 Clip 约 15 秒、纸面 ≥6 镜，写资产/特效/音效，Clip 之间写承接，能接成完整的一集。
5. **资产**：人物白底四视图一张合成（正面全身/侧面/背面/正面半身）；能复用就不新建。
6. **关键静帧 + 真实目视审查**：只出关键节拍，出完逐张放大对照错误清单审，不过就单张重出。
7. **图生视频**：用户明确放行后才生成。一条一条来，提示词全文粘贴，只挂 1 张参考图（最多 2 张），@ 正确的资产（不 @ 空壳），成片按顺序排好。

还有：台词风格指南（像真人说话、适量流行语、≤4 字/秒、可以跨条拆分）、打斗因果锁、风格锁模板、15 条通用错误台账。

## 目录

```
SKILL.md                         # 编排配方（Agent 入口）
templates/
  00-STYLE-LOCK.template.md      # 项目风格/语言/后端锁（可配置）
  01-adaptation-prompt.md        # 步骤1 改编提示词
  02-qa-rubric-100.md            # 步骤2 100 分验收表 + 硬否决
  03-pacing-checklist.md         # 步骤3 压节奏清单
  04-clip-storyboard.template.md # 步骤4 Clip 分镜模板
  05-asset-four-view-prompt.md   # 步骤5 四视图/场景/道具提示词
  06-still-audit-checklist.md    # 步骤6 关键静帧 + 目视审查
  07-video-prompt.template.md    # 步骤7 图生视频提示词 + 生成前清单
  dialogue-style-guide.md        # 台词与心声风格
  error-ledger.md                # 通用错误台账 G01–G15
examples/
  example-clip-prompt.md         # 一条虚构的步骤7 提示词示例
```

## 安装与使用

**Cursor**（Agent Skills）
```bash
git clone https://github.com/wwaa34682-lab/novel-to-short-drama-skill ~/.cursor/skills/novel-to-short-drama
# 或者放进项目：<project>/.cursor/skills/novel-to-short-drama
```

**Claude Code / 其他支持 `SKILL.md` 的 Agent**
```bash
git clone https://github.com/wwaa34682-lab/novel-to-short-drama-skill ~/.claude/skills/novel-to-short-drama
# 或者项目级：<project>/.claude/skills/novel-to-short-drama
```

不支持技能的工具：把 `SKILL.md` 当系统提示词或项目规则，需要哪一步就把对应模板贴进去。

**开工三件事**
1. 复制 `templates/00-STYLE-LOCK.template.md` 到项目里，填好题材、画风、面孔、昼夜、语言、模型。
2. 复制 `templates/error-ledger.md` 到项目里，之后每犯一个新错就追加一条。
3. 对 Agent 说：「按 novel-to-short-drama 技能，从步骤1 开始改编这段小说」，然后贴原文。

## 注意
- 请只改编你有权使用的作品，并遵守你所用平台的内容规范和版权要求。
- 生成会花钱：技能默认复用优先、单条重出、不整批刷，被安全审核拦下最多改写一次。

## 相关技能 / Related

- [jianying-desktop-editing](https://github.com/wwaa34682-lab/jianying-desktop-editing)：后期剪辑的后续技能。步骤7 的视频在剪映里拼好后，用它按剧情配乐（BGM）、保存和交付核验。/ Editing follow-up: story-driven BGM scoring and delivery checks in JianYing desktop.

## License
MIT，见 [LICENSE](LICENSE)。

---

## English summary

**novel-to-short-drama** is an agent skill (Cursor / Claude-style `SKILL.md`) that turns novel excerpts into AI-generated short-drama episodes through a 7-step, hard-gated pipeline: (1) plot-locked adaptation, (2) independent 100-point QA (≥95, no hard veto, every category at its floor), (3) short-video pacing (action → obstacle → action, keep causal bridges and breathing beats), (4) ~15 s clip storyboards with ≥6 shots each and clip-to-clip handoff, (5) assets (one-image white-background four-view character sheets, reuse first), (6) key-beat stills plus a real visual audit, and (7) image-to-video only after explicit human go-ahead, one clip per video, full prompt pasted, one reference image, correct asset tags. It ships a configurable style-lock template, a natural-dialogue guide, fight-scene causality rules, and a generic 15-item error ledger. Backend-agnostic (LibTV canvas + Seedance shown as an example). Docs are in Chinese. MIT licensed.
