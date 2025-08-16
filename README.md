<p align="center">
  <img alt="Omni 0 preview models header" src="https://github.com/omniomni-ai/omni-0-preview-models/raw/refs/heads/main/omni-0-preview-models-image.png">
</p>

<p align="center">
  <a href="https://github.com/omniomni-ai"><strong>GitHub</strong></a> &nbsp
   <a href="https://omniomni.framer.website/"><strong>Website</strong></a> &nbsp
    <strong>Paper (Coming Soon)</strong>
</p>

<br>

# Omni 0 Preview Models

Omni 0 preview models are a series of 1.7B parameter LLMs optimized for STEM knowledge consisting of 4 expert models and one final merged output between all experts. Experts include: [Science Expert](https://huggingface.co/omniomni/omni-0-science-preview),  [Technology Expert](https://huggingface.co/omniomni/omni-0-technology-preview), [Engineering Expert](https://huggingface.co/omniomni/omni-0-engineering-preview),  [Math Expert](https://huggingface.co/omniomni/omni-0-math-preview). Through DARE-TIES merging, Omni is able to achieve state-of-the-art efficiency and domain benchmark results among alternative optimization techniques, as well as optimal compute-knowledge efficiency across similar models.

<p align="center">
  <figure>
  <img src="https://github.com/omniomni-ai/omni-0-preview-models/raw/refs/heads/main/compute-knowledge-efficiency-plot.png"
       alt="Omni compute-knowledge efficiency plot">
  <figcaption>Omni achieves optimal compute-knowledge efficiency compared to alternative models</figcaption>
</figure>
</p>

> [!Note]
> This model card is for [omni-0-science-preview](https://huggingface.co/omniomni/omni-0-science-preview). All other models can be found on [Omni's HuggingFace page](https://huggingface.co/omniomni)

# Benchmarks
**Expert Model Benchmarks**
|Benchmark            | Science | Technology | Engineering | Math  |
|-------------------------------|------------------|---------------------|----------------------|----------------|
| MMLU Science (4-shot CoT)     | 26.69            | --                  | --                   | --             |
| SciQ (0-shot)                 | 85.80            | --                  | --                   | --             |
| ARC-Challenge (0-shot)        | 42.41            | --                  | --                   | --             |
| ARC-Easy (0-shot)             | 66.96            | --                  | --                   | --             |
| MMLU Technology (4-shot CoT)  | --               | 35.30               | --                   |                |
| Humaneval (pass@1)            | --               | 32.93               | --                   | --             |
| MMLU Engineering (4-shot CoT) | --               | --                  | 32.07                | --             |
| MMLU Math (4-shot CoT)        | --               | --                  | --                   | 30.83          |
| MATH (4-shot)                 | --               | --                  | --                   | 18.76          |
| Expert Average       | **36.28**   | **34.83**      | **32.07**       | **28.82** |
| Base Average         | 35.59            | 29.79               | 30.86                | 22.57          |
| Improvement          | 1.94\%           | 16.92\%             | 3.92\%               | 27.69\%        |
>[!Note]
>Expert average refers to the average of the expert model for the STEM domain in focus while benchmarking

<br>

**Omni-0-mini-preview Benchmarks**
| **Benchmark**                           | **Omni** | **Base** | **Alternative Models** | **Llama 3.2 3B** | **Gemma 3 4B** | **Llama 3.1 8B** |
|-----------------------------------------|----------|----------|------------------------|------------------|----------------|------------------|
| MMLU STEM (4-shot CoT)                  | **35.02** | 26.59    |                        | 33.28            | 40.82          | 52.22            |
| MMLU Science (4-shot CoT)               | **34.44** | 28.03    |                        | 33.47            | 42.93          | 52.54            |
| MMLU Technology (4-shot CoT)            | **41.07** | 30.86    |                        | 45.28            | 46.74          | 63.72            |
| MMLU Engineering (4-shot CoT)           | **37.50** | 25.93    |                        | 34.65            | 43.66          | 55.58            |
| MMLU Math (4-shot CoT)                   | **35.54** | 23.86    |                        | 39.51            | 35.31          | 45.84            |
| HumanEval (pass@1)                      | **31.71** | 29.88    |                        | 51.83            | 57.32          | 57.93            |
| SciQ (0-shot)                           | **87.30** | 76.10    |                        | 93.30            | 87.50          | 91.80            |
| MATH (4-shot)                           | 15.66     | **16.12**|                        | 28.44            | 26.38          | 29.56            |
| ARC-Challenge (0-shot)                  | **43.00** | 40.10    |                        | 46.16            | 44.11          | 54.18            |
| ARC-Easy (0-shot)                       | **66.67** | 58.54    |                        | 67.93            | 63.01          | 75.80            |
| **Average**                             | **37.91** | 30.25    |                        | 38.33            | 43.91          | 54.22            |
| **Improvement**                         | **25.32%**| Base     |                        |                  |                |                  |

# Models
Omni comes in a total of 5 models:

**Merged Model**
- `omni-0-mini-preview` - Merged output of all four experts through DARE-TIES, delivering large improvements in performance in STEM domains compared to its base.

**Experts**
- `omni-0-science-preview` - Science expert finetuned on corpora of scientific wikipedia texts and academic papers, as well as a chat-templated scientific Q&A dataset
- `omni-0-technology-preview` - Technology expert finetuned on chat-templated code generation data and stack exchange questions and top-voted answers
- `omni-0-engineering-preview` - Engineering expert finetuned on corpora of engineering-related wikipedia texts and academic papers
- `omni-0-math-preview` - Math expert finetuned on chat-templated math Q&A data

All Omni experts are finetuned from their base model: [SmolLM2 1.7B Instruct](https://huggingface.co/HuggingFaceTB/SmolLM2-1.7B-Instruct) on H100/Ada 6000/A100 GPUs, improving by 25.32% on average over all tested STEM benchmarks.

# Features

**Made for all** Omni is a series of highly efficient Large Language Models aimed at expanding the accessibility of AI, filling in its gaps among underserved populations.

**Efficient** Omni operates at optimal compute-knowledge efficiency compared to similar models.

**Merged architecture** Omni uses merging to provide the collective accuracy of specialized models, leveraging their capabilities to enhance the final merged model.
  
**Multi-disciplinary** Omni's first variant achieves state-of-the-art performance across STEM compared to alternative optimization techniques.

# Merging
This repository contains the merging configuration for omni-0-mini-preview. To replicate its merge, first install Arcee AI's mergekit:

```bash
git clone https://github.com/arcee-ai/mergekit.git
cd mergekit

pip install -e .  # install the package and make scripts available
```

After installing, clone this repository and set it as your terminal's current directory:

```bash
git clone https://github.com/omniomni-ai/omni-0-preview-models.git
cd omni-0-preview-models
```

In the directory, run:

```bash
# mergekit-yaml ./omni-0-mini-preview.yml ./omni-0-mini-preview
```

Running this command will now merge omni-0-mini-preview's expert models into a compact fused LLM through DARE-TIES.
