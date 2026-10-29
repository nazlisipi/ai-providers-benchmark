# AI Providers Benchmark

AIMultiple benchmark of seven API providers serving GPT-OSS-120B: CoreWeave Forge (formerly Weights & Biases), Cerebras, DeepInfra, Fireworks AI, Groq, Nebius and SambaNova. The study tracks daily accuracy and latency on each provider.

> [Read the benchmark on AIMultiple](https://aimultiple.com/ai-providers)

## Workload

The providers had the highest market share on OpenRouter, and GPT-OSS-120B is the most widely used open-source model there. All requests go through the same OpenRouter API endpoint and reach all providers simultaneously.

The test set has 108 questions: 35 real-world knowledge questions from CNN News articles and 73 math reasoning problems. The model scored 98% on this set when self-hosted on a RunPod H200 GPU instance. It consistently answers these questions correctly, so the test looks for quality drops by time of day or system load.

Each provider receives the full set every 5 minutes, and true/false results become daily accuracy averages. A fixed reference question sent with each submission measures first token latency (FTL) and end-to-end latency, averaged per day.

## Benchmark results

Daily average FTL on 2026-01-18, the last day in the latency chart:

| Provider | FTL (ms) |
| --- | ---: |
| Cerebras | 867.92 |
| Groq | 1079.84 |
| SambaNova | 1381.87 |
| Fireworks AI | 1692.51 |
| Nebius | 2155.58 |
| CoreWeave Forge (formerly W&B) | 3073.38 |
| DeepInfra | 4955.1 |

Fireworks AI's FTL fell from 3839.5 ms on 2026-01-15 to 1766.62 ms on 2026-01-16. SambaNova's daily accuracy dropped to 80.08% on 2026-01-10, the lowest value in the accuracy chart.

## Scope

Results apply to GPT-OSS-120B routed through OpenRouter between 2025-12-25 and 2026-01-18. A separate chart of blended prices and first token latency, outside the daily test, covers more models and providers.

## Ownership

The benchmark implementation was developed for AIMultiple and belongs to AIMultiple. This repository contains a documentation summary. Source code and benchmark datasets are not distributed here.
