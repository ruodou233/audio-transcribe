# local-config — 本机环境映射（模板）

> 复制为 `local-config.md` 并按你的环境填写；该文件含本机信息，不要提交到公开仓库。

## 云端 ASR

- 阿里云百炼（DashScope）API key 位置：`<如 ~/.config/dashscope/env>`
- 免费额度/欠费开关状态：`<确认"额度用完即停"开关已按需开启；欠费会导致所有调用失败>`
- 其他云端 ASR（可选）：`<引擎名 + key 位置>`

## 本地模型

- SenseVoice-Small：`<已装/未装；VAD 依赖是否就绪>`
- faster-whisper：`<已装/未装>`
- 本地 FunASR 生态（说话人分离）：`<已装/未装；不可上云场景的分离替代>`

## 会议纪要工具（便宜线，免费档以执行前核验为准）

- 飞书妙记或等价工具：`<CLI/权限是否可用；如 lark-cli 已认证>`

## 裁决与校对 LLM

- 分歧裁决模型：`<如 qwen-plus；失败回退模型>`
- 校对模型与调用入口：`<模型 + CLI/API>`

## 输出约定

- 转写产物目录：`<如 ~/transcripts/<项目名>/>`
- raw 稿与校对稿命名约定：`<raw.jsonl / corrected.md 等>`
