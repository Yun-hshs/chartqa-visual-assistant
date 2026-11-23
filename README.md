# 图表与短视频多模态视觉语言助手

方向 02 课程项目。用 Qwen2.5-VL-7B-Instruct 做 ChartQA LoRA 指令微调，在单张 RTX 5090 上部署 Gradio。支持高清单图、有序多图和短视频，并可切换基座对照。

[正式实验报告](02-Multimodal/phase1-assistant/reports/final-report.md) · [在线 Demo](https://dc9fa8a96886798c5a.gradio.live) · [一键启动](02-Multimodal/phase1-assistant/DEMO.md) · [实验复现](02-Multimodal/phase1-assistant/ABLATION.md)

| 完整 ChartQA test（2,500 题） | Human | Augmented | 总分 |
|---|---:|---:|---:|
| 基座 | 53.68% | 42.80% | 48.24% |
| rank 8 · step 256 | 74.72% | 92.72% | 83.72% |
| rank 16 · step 128 | 75.92% | 92.24% | 84.08% |

验证选点锁定后运行完整测试。总分包含数值与单位格式的影响，两个 rank 的 0.36 个百分点差异来自单种子结果与各自选点。

```bash
cd 02-Multimodal/phase1-assistant
# 环境、模型与 adapter 准备见 DEMO.md
SHARE=1 bash scripts/start_demo.sh
```

在线 Demo 是临时分享地址。页面内有三组可直接点击的自制样例。代码采用仓库 LICENSE。ChartQA 和模型权重按各自发布条款从上游获取。
