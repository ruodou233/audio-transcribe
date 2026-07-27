# local-config — 本机环境映射（模板）

> 复制为 `local-config.md` 并按你的环境填写；该文件含本机信息，不要提交到公开仓库。

## 云端账户与端点

| provider / profile alias | 凭证引用 | CLI / SDK 版本 | auth state | entitlement / endpoint | 额度状态 | probe kind / result | checked_at | reason code |
|---|---|---|---|---|---|---|---|---|
| `<服务 / 本地别名>` | `<官方凭证库、Keychain、Secret Store 或受限文件的引用；不填凭证值>` | `<路径与版本>` | `<verified / unverified / unavailable>` | `<可访问模型或端点>` | `<已知余额、免费额度、限额或 unknown>` | `<auth status / model list / 首次正式调用等>` | `<ISO 8601>` | `<not-installed / not-logged-in / no-entitlement / quota / network / unknown>` |

## 本地转写管线

| ASR | VAD | 说话人分离 | 对齐/时间戳 | 运行后端与版本 | 硬件 | probe kind / result | checked_at |
|---|---|---|---|---|---|---|---|
| `<模型>` | `<组件>` | `<组件或无>` | `<组件与粒度>` | `<CLI / Python / ONNX / vLLM 等>` | `<CPU/GPU/内存>` | `<短样本或版本探测结果>` | `<ISO 8601>` |

## 会议纪要或宿主连接器

| 能力 | 登录/连接状态 | 可导出格式 | 最近验证 | 备注 |
|---|---|---|---|---|
| `<会议纪要工具或宿主连接器>` | `<verified / unverified / unavailable>` | `<文本/时间戳/说话人等>` | `<ISO 8601>` | `<权限或限制>` |

## 裁决与校对 LLM

- 分歧裁决模型：`<如 qwen-plus；失败回退模型>`
- 校对模型与调用入口：`<模型 + CLI/API>`

## 状态记录约定

- `verified` 只对所记录的 provider/profile、模型或端点、探针和时间成立，不能由“已安装”推导“已登录”，也不能由“已登录”推导“指定模型可调用”。
- 用户在单次任务中拒绝补齐不写入本文件；只有用户明确给出长期范围时才记录范围。
- 市场价格、模型能力和官方链接不写在本文件，按 `references/asr-candidates.md` 与执行时官方资料核验。

## 输出约定

- 转写产物目录：`<如 ~/transcripts/<项目名>/>`
- raw 稿与校对稿命名约定：`<raw.jsonl / corrected.md 等>`
