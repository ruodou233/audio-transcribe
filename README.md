# audio-transcribe — 音频转文字 Skill

## 这是什么

`audio-transcribe` 帮 Agent 把普通话录音、播客、会议或视频转成可靠文字稿。它优先复用当前电脑已有能力并立即开工；普通话 ASR 评测、免费额度和更优路线在后台并行查询，不挡住转写。

## 使用时会怎么做

1. 先看手头是否已经有文字稿或字幕。
2. 读取已有的 `local-config.md`；没有就轻量探测当前电脑。
3. 有可执行管线就立即派子代理转写，不等待联网选型。
4. 普通话准确率榜、稳定评测集和官方免费额度并行查询。
5. 先交付文字稿，再补充有免费额度、完全免费和高质量的其他方案。

用户可以直接指定说话人、时间戳、SRT/VTT/JSON、是否允许上云和质量要求；没有指定时默认交付可读纯文本，并优先使用不新增费用的现成方案。

## 普通话选型

[`references/asr-benchmarks.md`](references/asr-benchmarks.md) 只保存普通话网络内容、会议、访谈、播客和专业领域的评测入口，不保存会过期的模型排名、价格和额度。具体选择在任务发生时实时核验。

## 安装

Claude Code：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/ruodou233/audio-transcribe.git ~/.claude/skills/audio-transcribe
```

Codex：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/ruodou233/audio-transcribe.git ~/.codex/skills/audio-transcribe
```

或通过 [agentops-skills](https://github.com/ruodou233/agentops-skills) 安装整套 Skill。

安装后可以直接说：“把这个播客转成带说话人和时间戳的文字稿。”

## 反馈与作者

- GitHub：本仓库提 issue 或 PR
- 小红书：错误乱码
- 微信公众号：能工智人错误乱码
- B站：若逗道人

## License

MIT
