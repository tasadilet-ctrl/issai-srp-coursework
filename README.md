# ISSAI SRP Coursework

Workshop and practice notebooks completed during ISSAI's Summer Research Program (SRP) — covering ML fundamentals, from-scratch implementations, and a paper reproduction.

| Notebook | Topic |
|---|---|
| [`practice-1/`](practice-1/Practice%231.ipynb) | NumPy fundamentals for ML — arrays, vectorized ops |
| [`convolution-scratch/`](convolution-scratch/p1_convolution_from_scratch.ipynb) | Convolution and edge detection implemented from scratch |
| [`monday-primer/`](monday-primer/monday_primer.ipynb) | Tokenization — how LLMs read text, and why it's harder for Kazakh |
| [`transformer-workshop/`](transformer-workshop/workshop1_inside_the_transformer.ipynb) | Inside the transformer — embeddings, attention, sampling temperature |
| [`highschool-task/`](highschool-task/student_task_highschool.ipynb) | Reproducing "Crazy Heads" from the Calm-Whisper paper (arXiv:2505.12969) |
| [`university-task/`](university-task/student_task_university.ipynb) | Extended version of the Calm-Whisper reproduction task |
| [`workshop2-asr-evaluation/`](workshop2-asr-evaluation/workshop2_asr_inference_and_evaluation.ipynb) | ASR inference & evaluation — Whisper vs. two Omnilingual ASR variants (CTC vs. autoregressive), compared on speed and WER |
| [`homework2-asr-scoreboard/`](homework2-asr-scoreboard/homework2_kazakh_asr_scoreboard.ipynb) | Kazakh ASR model selection for two deployment scenarios (office vs. call center) — WER/CER/latency leaderboard, frontier plot, and a defended trade-off pick |

## Calm-Whisper reproduction

Whisper (OpenAI's speech-to-text model) hallucinates text when fed audio with no speech at all. The Calm-Whisper paper (arXiv:2505.12969) traces this to a small set of attention heads ("crazy heads") and shows how suppressing them reduces hallucination. Both task notebooks reproduce this finding at different depths.

## ASR model selection

`workshop2-asr-evaluation` walks through running and evaluating ASR models on a single Kazakh clip. `homework2-asr-scoreboard` builds on it: benchmark several ASR models (WER, CER, latency) under both clean and telephony conditions, plot the WER-vs-latency frontier, and defend a model choice for a call-center deployment. [`stream_realtime_README.md`](homework2-asr-scoreboard/stream_realtime_README.md) specs an optional real-time streaming-transcription extension.

## Setup

[`student_setup.md`](student_setup.md) — the workstation setup steps used to open each workshop (SSH connection, `uv` virtual environment).
