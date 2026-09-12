# 普通话音视频转文字｜Mandarin Speech-to-Text

Transcribe Mandarin recordings, podcasts, meetings, and videos with speaker labels, timestamps, subtitles, and transcript review.

## 这是什么

手里有段录音或视频，想把里面的话留下来，就交给 `audio-transcribe`。它帮 Agent 把普通话会议、访谈、播客、课程和个人录音转成文字稿或字幕，也能核验已有的自动稿。先复用当前电脑能跑的转写能力开工，普通话评测、免费额度和更好的路线同时在后台查。

## 这些音视频都可以转

- **会议和访谈**：“把这段录音转成带说话人和时间戳的文字稿。”方便按人查找发言，或回到音频里核对某句话。
- **播客和课程**：“这期播客帮我转成可读的纯文本。”把需要反复拖进度条的内容变成能搜索、能标记的文字，后续查资料时更方便。
- **视频字幕**：“给这段视频做一份 SRT 字幕。”也可以指定 VTT 或 JSON，把时间信息和文本按后续要用的格式交出来。
- **核对已有自动稿**：“我有音频和自动字幕，帮我核一下人名、术语和听错的地方。”利用现成稿件继续校对，让最容易出错的部分有原音可查。

说清楚要不要区分说话人、要什么格式即可；不指定时，默认交付可读纯文本。

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
