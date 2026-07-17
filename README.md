# audio-transcribe — 音频转文字全流程 skill

把音频/播客/视频变成可靠文字稿的完整决策流程：**判断有没有现成稿 → 按预算和质量要求选方案 → 转写 → LLM 上下文校对**。快速稿一条线跑完；精确稿（多人访谈/播客逐字稿）用双 ASR 交叉验证 + 说话人分离 + 分歧裁决，实战验证过 3 小时双人访谈播客的产出。

## 30 秒安装

Claude Code：

```bash
git clone https://github.com/ruodou233/audio-transcribe.git ~/.claude/skills/audio-transcribe
```

Codex：

```bash
git clone https://github.com/ruodou233/audio-transcribe.git ~/.agents/skills/audio-transcribe
```

或用聚合仓一次装全部 skill：见 [agentops-skills](https://github.com/ruodou233/agentops-skills)。

装好后对你的 Agent 说"把这个播客转成逐字稿"即可触发。

## 核心亮点

- **不同价格的方案全覆盖**：从零成本（飞书妙记、本地 SenseVoice/faster-whisper）到低价云端（阿里百炼 fun-asr，≈¥13.2/千分钟）到高精度返工（gpt-4o-transcribe），按场景给经验法则。
- **按质量要求分档**：快速稿单线转写直接交付，双 ASR/裁决/回听全跳过；精确稿才走完整管线——不为不需要的精度付流程成本。
- **现成稿智能判断**：官方节目、知名播客先搜现成稿（官方精校 > 平台字幕 > 媒体实录）；小众内容不浪费时间直接转写。
- **多人录音效果好**：双引擎交叉验证，一致部分直接采信，只把分歧片段送 LLM 裁决——省 token 且不让 LLM 有机会编造。
- **LLM 校对就是要凭上下文改错**：同音字、专名、术语大胆修正（这正是再审一遍的目的），但只修识别错误、不动表达本身；人名/作品名等能联网查实的用强模型检索确定，高风险分歧回听原音频，全部修改 diff 留痕。
- **原话保护 + 可追溯验收**：raw 稿永不覆盖，修改全部 diff 留痕，关键片段回听抽检。
- **踩坑速查**：时间轴单位误判、固定窗对齐假阳性、SenseVoice 必须配 VAD 等实战教训直接写进流程。

## 环境要求

- 本 skill 是给 Agent 的决策与执行指南：转换、对齐、校验脚本由你的 Agent 按 SKILL.md 的统一数据格式与校验断言现场生成，不随包提供固定实现。
- 转写引擎按你实际拥有的来：任一云端 ASR（需 API key）或本地模型（SenseVoice-Small/faster-whisper + VAD）都可按对应分支执行或接入现有工具；双 ASR 管线需要至少两条厂商差异大的引擎。
- 音频预处理只需系统自带工具（macOS afconvert）或等价物。
- 首次使用按 SKILL.md「环境自适应」节探测你的环境并填写 `local-config.md`（模板见 [local-config.example.md](local-config.example.md)，该文件已被 .gitignore 排除，不会被误提交）。

价格与接口限制以各平台当期官方文档为准（本文数字为作者 2026-07 实测）。

## License

MIT
