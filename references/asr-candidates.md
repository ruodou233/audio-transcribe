# ASR 候选发现参考

> 这是候选种子，不是默认排名。能力、价格、地域和模型权限会变化；进入实际管线前按当前任务和官方资料复核。最近整理：2026-07-28。

## 发现规则

1. 先查使用者已配置的本地模型、云端账户、会议纪要工具和宿主连接器。
2. 只有当前候选不足、资料过期或用户要求比较时，才扩展搜索主流专用 STT API 与开源本地 ASR。
3. 只纳入官方能力、限制和调用入口可核验，且满足当前语言、隐私与输出要求的候选。
4. 价格在收费调用前核验；余额、免费额度、地域与模型权限在执行前核验。无法核验时标记「未核验」。
5. 把 ASR、VAD、说话人分离、强制对齐和导出视为可组合组件；官方未列某能力时写「官方材料未列」，不写绝对不存在。

## 已核验候选种子

| 候选 | 形态 | 已核验能力与限制 | 官方来源 |
|---|---|---|---|
| Qwen3-ASR 0.6B/1.7B | 本地开源 / 云 API | 30 种语言 + 22 种中文方言，离线/流式；时间戳需独立 ForcedAligner，后者覆盖 11 种语言；官方材料未列内置说话人分离 | https://github.com/QwenLM/Qwen3-ASR |
| Whisper `turbo` | 本地开源 | `large-v3` 的加速版本；通用多语基线，语言表现需用任务样本复测 | https://github.com/openai/whisper |
| SenseVoice / FunASR | 本地开源生态 | ASR、VAD、标点、说话人相关组件可组合；具体模型和端到端管线需逐项验证 | https://github.com/modelscope/FunASR |
| OpenAI Transcribe 系列 | 云 API | `gpt-4o-transcribe`、mini 与 diarize 分工不同；diarize 支持说话人标注，但不支持普通模型的全部提示词或时间戳参数 | https://platform.openai.com/docs/api-reference/audio |
| Voxtral Mini Transcribe 2 | 云 API | 说话人分离、上下文偏置、词级时间戳、13 种语言；单次录音时长限制按当期文档核验 | https://docs.mistral.ai/studio-api/audio/overview |
| Google Cloud Chirp 3 | 云 API | 多语、语音适配与说话人分离；分离能力受语言和调用方法限制 | https://docs.cloud.google.com/speech-to-text/v2/docs/chirp-model |
| Gemini 音频理解 | 通用多模态云模型 | 可按提示转录、区分说话人和引用时间段；不能默认视为专用 STT 的同等级时间轴方案 | https://ai.google.dev/gemini-api/docs/audio |
Deepgram、AssemblyAI 等其他服务遵循同一准入规则：进入候选池需官方可核验；进入立即执行清单还需当前环境可调用。不要为了让列表看起来完整而无限罗列。

## 任务级待核验候选

Azure Speech、AWS Transcribe、阿里云 ASR、Deepgram、AssemblyAI 与会议纪要工具等，只在当前使用者已拥有账户/连接器或任务约束需要时进入候选池；逐项从当期官方文档或控制台核验语言、说话人、时间戳、热词、长音频、价格、地域与数据处理条件。未完成核验前不得列入“已核验候选种子”或立即执行清单。
