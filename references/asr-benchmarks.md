# 中文 ASR 选型入口

本文件只保存评测入口，不保存当前模型排名、价格或免费额度。

| 素材场景 | 入口 | 重点切片 |
|---|---|---|
| 中文方言、专业领域、复杂真实音频 | https://github.com/SpeechColab/GigaSpeechBench | 中文方言与中文垂直领域 CER / B-CER |
| 普通话网络内容、播客、远场会议 | https://github.com/wenet-e2e/WenetSpeech | TEST_NET / TEST_MEETING |
| 新闻、访谈、直播、播客、演讲 | https://github.com/SpeechColab/Leaderboard | 对应 SpeechIO 中文场景 |
| 粤语 | https://github.com/ASLP-lab/WenetSpeech-Yue | WSYue-eval 对应子集 |
| 四川话 | https://github.com/ASLP-lab/WenetSpeech-Chuan | WSC-Eval-ASR Easy / Hard / Total |

先选与素材最接近的场景，再比较同一测试集、同一模式下的中文 CER。榜单用于校准现成管线和发现更优候选；本机已有方案能完成任务时，不等待榜单查询才开始转写。

准确率榜不等于实时性能榜。需要流式字幕时，另看候选服务当期的延迟、增量稳定性和流式接口；免费额度与价格也在执行时从官方页面核验。
