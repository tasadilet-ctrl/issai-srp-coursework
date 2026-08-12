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

## Calm-Whisper reproduction

Whisper (OpenAI's speech-to-text model) hallucinates text when fed audio with no speech at all. The Calm-Whisper paper (arXiv:2505.12969) traces this to a small set of attention heads ("crazy heads") and shows how suppressing them reduces hallucination. Both task notebooks reproduce this finding at different depths.
