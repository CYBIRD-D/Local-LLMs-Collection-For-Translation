# Local LLMs for Translation

A curated list of local and open-weight LLMs under 14B that may be useful for translation tasks.

Translation quality depends on the language pair, model size, fine-tuning data, quantization, prompt style, and the type of content being translated. The models listed here may or may not meet your expectations in every use case.

For more background, see [Models & Performance](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/FAQ_EN.md#models--performance).

## Table of Contents

- [What is this?](#what-is-this)
- [How to Choose a Model](#how-to-choose-a-model)
- [Legend](#legend)
- [Essential Reading](#essential-reading)
- [Model Families](#model-families)
- [How to Read Model Names](#how-to-read-model-names)
- [General Notes](#general-notes)
- [**Model List by VRAM**](#model-list-by-vram)
  - [0–3B / VRAM ≤ 4GB](#03b--vram--4gb)
  - [4B–5B / VRAM ≈ 4–6GB](#4b5b--vram--46gb)
  - [7B–10B / VRAM ≈ 6–8GB](#7b10b--vram--68gb)
  - [12B–14B / VRAM ≈ 12–16GB](#12b14b--vram--1216gb)
- [**Model List by Language Index**](#language-index)
- [Disclaimer](#disclaimer)

## What is this?

This README is a compact collection of small and mid-sized local LLMs that can be used for translation.

The list focuses on:

- models under 14B parameters;
- models that are practical for local deployment;
- models with GGUF availability when possible;
- models with community attention, downloads, likes, language-specific fine-tuning, or reported translation usefulness.

The list is not a benchmark. It is a navigation page for finding models worth testing.

## How to Choose a Model

A simple selection path:

1. **Check your available VRAM first.** Local model choice is usually limited by GPU memory.
2. **Choose by language pair.** A smaller model fine-tuned for your language pair may beat a larger general model.
3. **Prefer tested models marked with `★`.** The mark means the model has been tested on some languages or tasks.
4. **Prefer GGUF if you use llama.cpp-based tools.** This includes LM Studio, Ollama, Kobold, and similar local frontends.
5. **Use stronger quantization if VRAM allows.** `Q5_K` and above usually have no noticeable quality loss for many use cases.
6. **Test with your own content.** Translation quality varies heavily across novels, subtitles, technical text, UI strings, casual chat, and document translation.
> Read [How to choose a LLM-Local models](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/README_en.md#local-models-open-weight--open-source) for more details

| VRAM Tier | Required VRAM | Note |
|---|---:|---|
| 0~3B | Vram≤4GB |  low vram/cpu |
| 4B/5B | Vram≈4GB~6GB | Small local models/cpu |
| 7B-10B | Vram≈6G~8G | Usually decent translation quality |
| 12B-14B | Vram≈12G~16G | Larger local models around 14B± |

## Legend

| Term / Symbol | Meaning |
|---|---|
| `★` | Tested on some languages or tasks |
| GGUF | Common model format for llama.cpp, LM Studio, Ollama, Kobold, etc. |
| General multilingual | Broad multilingual capability, not necessarily specialized for one language pair |
| EN ⇌ XX | English to/from multiple languages |
| JP | Japanese |
| ZH | Chinese |
| KO | Korean |
| RU | Russian |
| FR | French |
| ES | Spanish |
| UKR | Ukrainian |
| BG | Bulgarian |
| TR | Turkish |
| SEA | Southeast Asian languages |
| ne | Nepali |
| **Abliterated / uncensored / heretic / amoral / evil / ara** | Safety-reduced fine-tune styles. Use with caution and test output quality yourself. |

## Essential Reading

Read these first if you are new to local LLMs:

- [**★LLM VRAM usage lists**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md)
  - [GGUF quantization types & relative quality](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)
- [Deploy local models](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/tree/main#deploying-local-models)
- [**★How to choose an LLM? Online vs Local**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)
  - [Local models](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/README_en.md#local-models-open-weight--open-source)
- [FAQ - Frequently Asked Questions](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/FAQ_EN.md)
- [**★Free LLM API Providers**](https://github.com/CYBIRD-D/FREE-LLM-API-Provider)

## Model Families

<details>
<summary>Models below include base models and fine-tunes from Qwen, Gemma, Mistral, Hunyuan, and other families.</summary>

- Qwen
  - [Qwen 3 1.7B/4B/8B/14B](https://huggingface.co/collections/Qwen/qwen3)
  - [Qwen 3 VL 2B/4B/8B](https://huggingface.co/collections/Qwen/qwen3-vl)
- Gemma
  - [Gemma 3 4B/12B](https://huggingface.co/collections/google/gemma-3-release)
  - [Gemma 3n E2B/E4B](https://huggingface.co/collections/google/gemma-3n)
  - [Gemma 4 E2B/E4B](https://huggingface.co/collections/google/gemma-4)
- Mistral
  - [Ministral 3B/8B/14B](https://huggingface.co/collections/mistralai/ministral-3)
  - [Mistral Nemo 12B](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407)

</details>

## How to Read Model Names

Example: **Qwen3-8B-Thinking-2507-abliterated-Q8_0-gguf**

This model name is hypothetical and only used for illustration.

- **Qwen3**: base model family.
- **8B**: parameter count. Common sizes include 4B, 8B, 14B, 30B, 70B, and larger.
- **Thinking**: indicates a thinking-mode model. Not all thinking models are explicitly labeled.
- **2507**: time tag, usually meaning 2025/07 or a similar release/update marker.
- **abliterated**: a safety-reduced fine-tune style. Similar terms include **uncensored**, **NSFW**, **heretic**, **amoral**, and **evil**.
- **Q8_0 / GGUF**: llama.cpp quantization type and file format.

For VRAM and parameter-size guidance, see the [LLM VRAM usage lists](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md).

## General Notes

> **Notes**
>
> 1. Quantizations from **`Q5_K`** and above usually have no noticeable quality loss in many practical cases.
> 2. Larger model size × better data × more compute usually means better performance, but language-specific fine-tuning can change the result.
>    - Example: Qwen3-4B < Qwen3-8B < Qwen3-14B < Qwen3-32B.
> 3. Translation quality also depends on the quality and amount of training data for the target language pair.

**Download the GGUF file** unless you are not using a llama.cpp-based backend, such as LM Studio, Ollama, Kobold, or similar tools.

For **Mac** with Apple silicon, see [LM Studio with Apple MLX](https://lmstudio.ai/blog/lmstudio-v0.3.4).

## Model List by VRAM

### 0–3B / VRAM ≤ 4GB
LLMs at this scale usually have limited translation quality.<br>
All links are from Hugging Face.<br>
Models are selected based on **community reports, downloads, likes, and fine-tuning languages**.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| shisa-ai/shisa-v2.1-lfm2-1.2b <br> shisa-ai/shisa-v2.1-llama3.2-3b <br> LiquidAI/LFM2.5-1.2B-JP-202606 | **JP ⇌ EN** | LFM2 <br> Llama3.2 <br> LFM2.5 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-lfm2-1.2b-GGUF) <br> [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-llama3.2-3b-GGUF) <br> [GGUF](https://huggingface.co/LiquidAI/LFM2.5-1.2B-JP-202606-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-lfm2-1.2b) <br> [Original](https://huggingface.co/shisa-ai/shisa-v2.1-llama3.2-3b) <br> [Original](https://huggingface.co/LiquidAI/LFM2.5-1.2B-JP-202606) |
| LGAI-EXAONE/EXAONE-4.0-1.2B                       | **ES ⇌ EN ⇌ KO** | EXAONE4.0 | [GGUF](https://huggingface.co/LGAI-EXAONE/EXAONE-4.0-1.2B-GGUF) | [Original](https://huggingface.co/LGAI-EXAONE/EXAONE-4.0-1.2B) |
| tencent/HY-MT1.5-1.8B <br>  **★tencent/HY-MT2-1.8B**         | General multilingual <br> (33 languages) | HY-MT1.5 <br> HY-MT2 | [GGUF](https://huggingface.co/mradermacher/HY-MT1.5-1.8B-GGUF) <br> [GGUF](https://huggingface.co/mradermacher/Hy-MT2-1.8B-GGUF) | [Original](https://huggingface.co/tencent/HY-MT1.5-1.8B) <br> [Original](https://huggingface.co/tencent/Hy-MT2-1.8B) |
| Unbabel/Tower-Plus-2B                             | General | Gemma2 | [GGUF](https://huggingface.co/DZgas/Tower-Plus-2B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-2B) |
| prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1 | **EN ⇌ XX** [^1] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-2B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1) |
| Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-1.7B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1) |
| mistralai/Ministral-3-3B-Instruct-2512  | General | Mistral3 | [GGUF](https://huggingface.co/unsloth/Ministral-3-3B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-3B-Instruct-2512) |
| tiiuae/Falcon-H1-1.5B-Deep-Instruct <br> tiiuae/Falcon-H1-3B-Instruct  | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-1.5B-Deep-Instruct-GGUF) <br> [GGUF](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-1.5B-Deep-Instruct) <br> [Original](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct) |
| CohereLabs/tiny-aya series (3b)                            | General | aya | Same link | [Original Collection](https://huggingface.co/collections/CohereLabs/tiny-aya) |


---------

### 4B–5B / VRAM ≈ 4–6GB

> **`★` means model has been tested on some languages/tasks**.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| sarvamai/sarvam-translate  (note: 4B) | **22 official Indian languages**[^2] | Gemma3 | [GGUF](https://huggingface.co/mradermacher/sarvam-translate-GGUF) | [Original](https://huggingface.co/sarvamai/sarvam-translate) |  
| INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0 | **UKR ⇌ EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-4B-IT-v1.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0) |
| INSAIT-Institute/BgGPT-Gemma-3-4B-IT | **BG ⇌ EN** | Gemma3 | [GGUF](https://huggingface.co/INSAIT-Institute/BgGPT-Gemma-3-4B-IT-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/BgGPT-Gemma-3-4B-IT) |
| google/translategemma-4b-it    | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/translategemma-4b-it-GGUF) | [Original](https://huggingface.co/google/translategemma-4b-it) |
| ★mlabonne/gemma-3-4b-it-abliterated-v2      | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-4b-it-abliterated-v2-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-4b-it-abliterated-v2) | 
| p-e-w/gemma-4-E2B-it-heretic-ara      | General | Gemma4 | [GGUF](https://huggingface.co/mradermacher/gemma-4-E2B-it-heretic-ara-GGUF) | [Original](https://huggingface.co/p-e-w/gemma-4-E2B-it-heretic-ara) | 
| himalaya-ai/himalaya-gemma-4-e2b-it   | **NE ⇌ EN** | Gemma4 | [GGUF](https://huggingface.co/himalaya-ai/himalaya-gemma-4-e2b-it-gguf) | [Original](https://huggingface.co/himalaya-ai/himalaya-gemma-4-e2b-it) | 
| ★Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2 | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2) | 
| RefalMachine/RuadaptQwen3-4B-Instruct | **RU ⇌ EN** | Qwen3 | [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct-GGUF) | [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct) | 
| **★SakuraLLM/GalTransl-v4-4B-2601** | **JP ⇌ ZH** | Qwen3 | [GGUF](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2601) | [Original](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2601) | 
| ★DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored (***[!]long thinking***[^3]) | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored-GGUF) | [Original](https://huggingface.co/DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored) | .
| prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1 | **EN ⇌ XX** | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-4B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1) | 
| aisingapore/Qwen-SEA-LION-v4-4B-VL <br> aisingapore/Gemma-SEA-LION-v4.5-E2B-IT | **EN + 7 key SEA languages**[^4] | Qwen3VL <br> Gemma 4 | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-4B-VL-GGUF) <br> [GGUF](https://huggingface.co/aisingapore/Gemma-SEA-LION-v4.5-E2B-IT-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-4B-VL) <br> [Original](https://huggingface.co/aisingapore/Gemma-SEA-LION-v4.5-E2B-IT) |  
| HiTZ/Latxa-Qwen3-VL-4B-Instruct <br> HiTZ/Latxa-Qwen3.5-4B | **(Basque-adapted) 5+**[^5] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Latxa-Qwen3-VL-4B-Instruct-GGUF) <br> N/A | [Original](https://huggingface.co/HiTZ/Latxa-Qwen3-VL-4B-Instruct) <br> [Original](https://huggingface.co/HiTZ/Latxa-Qwen3.5-4B) | 
| MuXodious/gemma-3n-E2B-it-absolute-heresy (5B / **CPU-optimized**)[^6]  | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E2B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E2B-it-absolute-heresy) |  



-------

### 7B–10B / VRAM ≈ 6–8GB
New LLMs at this size usually provide decent translation quality.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| tiiuae/Falcon-H1-7B-Instruct  | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct) |
| **★tencent/Hunyuan-MT2-7B**  | General multilingual (33 languages) | HY-MT2 | [GGUF](https://huggingface.co/mradermacher/Hy-MT2-7B-GGUF) | [Original](https://huggingface.co/tencent/Hy-MT2-7B) |
| ★MuXodious/gemma-3n-E4B-it-absolute-heresy (7B/CPU-optimized) | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E4B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E4B-it-absolute-heresy) |  
| ★google/gemma-4-E4B-it (8B / **CPU-optimized** / **MTP speedup**)  | General | Gemma4 | [GGUF](https://huggingface.co/unsloth/gemma-4-E4B-it-GGUF) | [Original](https://huggingface.co/google/gemma-4-E4B-it) <br> [MTP](https://huggingface.co/google/gemma-4-E4B-it-assistant) |  
| ★**Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-8B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1) |  
| ★**mlabonne/Qwen3-8B-abliterated** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-8B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-8B-abliterated) |  
| AvitoTech/avibe  (8B)<br> t-tech/T-lite-it-2.1  (8B)<br>RefalMachine/RuadaptQwen3-8B-Hybrid | **RU ⇌ EN** | Qwen3 | [GGUF](https://huggingface.co/NightForger/avibe-GGUF)<br> [GGUF](https://huggingface.co/t-tech/T-lite-it-2.1-GGUF) <br> [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid-GGUF) | [Original](https://huggingface.co/AvitoTech/avibe) <br> [Original](https://huggingface.co/t-tech/T-lite-it-2.1) <br> [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid) |  
| legmlai/legml-v1.0-8b-instruct | **FR ⇌ EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/legml-v1.0-8b-instruct-GGUF) | [Original](https://huggingface.co/legmlai/legml-v1.0-8b-instruct) |  
| **★shisa-ai/shisa-v2.1-qwen3-8b** <br> nvidia/NVIDIA-Nemotron-Nano-9B-v2-Japanese  | **JP ⇌ EN** | Qwen3 <br> Nemotron 2 Nano | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-qwen3-8b-GGUF) <br> [GGUF](https://huggingface.co/mmnga-o/NVIDIA-Nemotron-Nano-9B-v2-Japanese-gguf) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-qwen3-8b) <br> [Original](https://huggingface.co/nvidia/NVIDIA-Nemotron-Nano-9B-v2-Japanese) |  
| **★prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2** | **EN ⇌ XX** | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-8B-Instruct-abliterated-v2.0-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2) | 
| aisingapore/Qwen-SEA-LION-v4-8B-VL | **EN + 7 key SEA languages**[^4] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-8B-VL-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-8B-VL) | 
| **★SakuraLLM/Sakura-GalTransl-7B-v3.7** | **JP ⇌ ZH** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) |  
| ★mistralai/Ministral-3-8B-Instruct-2512 | General | Ministral3 | [GGUF](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512) | 
| lenML/aya-expanse-8b-abliterated | General | aya23 | [GGUF](https://huggingface.co/mradermacher/aya-expanse-8b-abliterated-GGUF) | [Original](https://huggingface.co/lenML/aya-expanse-8b-abliterated) |
| ★Unbabel/Tower-Plus-9B | General | Gemma2 | [GGUF](https://huggingface.co/mradermacher/Tower-Plus-9B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-9B) |
| KORMo-Team/KORMo-10B-sft <br> LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct <br> skt/A.X-4.0-Light | **KO ⇌ EN** | KORMo <br> EXAONE-3.5 <br> Qwen2.5 | [GGUF](https://huggingface.co/mradermacher/KORMo-10B-sft-GGUF) <br> [GGUF](https://huggingface.co/mradermacher/EXAONE-3.5-7.8B-Instruct-GGUF) <br> [GGUF](https://huggingface.co/mykor/A.X-4.0-Light-gguf) | [Original](https://huggingface.co/KORMo-Team/KORMo-10B-sft) <br> [Original](https://huggingface.co/LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct) <br> [Original](https://huggingface.co/skt/A.X-4.0-Light) |


----------


### 12B–14B / VRAM ≈ 12–16GB

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| ★Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-14B-abliterated-v3-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3) |  
| ★mlabonne/Qwen3-14B-abliterated  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-14B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-14B-abliterated) |  
| NousResearch/Hermes-4-14B  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Hermes-4-14B-GGUF) | [Original](https://huggingface.co/NousResearch/Hermes-4-14B) |  
| Sunbird/Sunflower-14B | **Ugandan languages[^7] ⇌ EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/Sunbird/Sunflower-14B) |  
| suayptalha/Sungur-14B | **TR ⇌ EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/suayptalha/Sungur-14B) | 
| sugoitoolkit/Sugoi-14B-Ultra-HF | **JP ⇌ EN** | Qwen2.5 | [GGUF](https://huggingface.co/mradermacher/Sugoi-14B-Ultra-HF-GGUF) | [Original](https://huggingface.co/sugoitoolkit/Sugoi-14B-Ultra-HF) |
| ★SakuraLLM/Sakura-GalTransl-14B-v3.8 | **JP ⇌ ZH** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) |
| **google/gemma-4-12B-it** <br> **★google/gemma-4-12B-it-qat**(8G VRAM support) <br> **★coder3101/gemma-4-12B-it-qat-q4_0-unquantized-heretic**(8G VRAM support) | General multilingual (**except Chinese**) | Gemma4 | [GGUF](https://huggingface.co/unsloth/gemma-4-12b-it-GGUF) <br> [GGUF](https://huggingface.co/unsloth/gemma-4-12B-it-qat-GGUF) <br> [GGUF](https://huggingface.co/SC117/gemma-4-12B-it-heretic-QAT-GGUF) | [Original](https://huggingface.co/google/gemma-4-12B-it) <br> [Original](https://huggingface.co/google/gemma-4-12B-it-qat-q4_0-unquantized) <br> [Original](https://huggingface.co/coder3101/gemma-4-12B-it-qat-q4_0-unquantized-heretic) |
| **★google/translategemma-12b-it** | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/translategemma-12b-it-GGUF) | [Original](https://huggingface.co/google/translategemma-12b-it) |
| INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0 <br> INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v2.0 | **UKR ⇌ EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-12B-IT-v1.0-GGUF) <br> [GGUF](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v2.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0) <br> [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v2.0) |
| INSAIT-Institute/BgGPT-Gemma-3-12B-IT | **BG ⇌ EN** | Gemma3 | [GGUF](https://huggingface.co/INSAIT-Institute/BgGPT-Gemma-3-12B-IT-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/BgGPT-Gemma-3-12B-IT) |
| ★mlabonne/gemma-3-12b-it-abliterated-v2 <br> mlabonne/gemma-3-12b-it-qat-abliterated | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-abliterated-v2-GGUF) <br> [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-qat-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-abliterated-v2) <br> [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-qat-abliterated) |
| ★mistralai/Ministral-3-14B-Instruct-2512 | General | Ministral | [GGUF](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512) |
| jenerallee78/Ministral-3-14B-abliterated | General | Ministral | [GGUF](https://huggingface.co/mradermacher/Ministral-3-14B-abliterated-GGUF) | [Original](https://huggingface.co/jenerallee78/Ministral-3-14B-abliterated) |
| mistralai/Mistral-Nemo-Instruct-2407 | General | Mistralnemo | [GGUF](https://huggingface.co/MaziyarPanahi/Mistral-Nemo-Instruct-2407-GGUF) | [Original](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407) |
| Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24 | **RU ⇌ EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/Vikhr-Nemo-12B-Instruct-R-21-09-24-GGUF) | [Original](https://huggingface.co/Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24) |
| **★shisa-ai/shisa-v2-mistral-nemo-12b** | **JP ⇌ EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/shisa-v2-mistral-nemo-12b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2-mistral-nemo-12b) |


--------


## Language Index

Use this section as a second entry point if you already know your target language pair.

### Japanese ⇌ Chinese

- SakuraLLM/GalTransl-v4-4B-2601
- SakuraLLM/Sakura-GalTransl-7B-v3.7
- SakuraLLM/Sakura-GalTransl-14B-v3.8

### Japanese ⇌ English

- shisa-ai/shisa-v2.1-lfm2-1.2b
- shisa-ai/shisa-v2.1-llama3.2-3b
- LiquidAI/LFM2.5-1.2B-JP-202606
- shisa-ai/shisa-v2.1-qwen3-8b
- NVIDIA-Nemotron-Nano-9B-v2-Japanese
- sugoitoolkit/Sugoi-14B-Ultra-HF
- shisa-ai/shisa-v2-mistral-nemo-12b

### Korean ⇌ English

- LGAI-EXAONE/EXAONE-4.0-1.2B
- KORMo-Team/KORMo-10B-sft
- LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct
- skt/A.X-4.0-Light

### Russian ⇌ English

- RefalMachine/RuadaptQwen3-4B-Instruct
- AvitoTech/avibe
- t-tech/T-lite-it-2.1
- RefalMachine/RuadaptQwen3-8B-Hybrid
- Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24

### Ukrainian / Bulgarian / Turkish ⇌ English

- INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0
- INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0
- INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v2.0
- INSAIT-Institute/BgGPT-Gemma-3-4B-IT
- INSAIT-Institute/BgGPT-Gemma-3-12B-IT
- suayptalha/Sungur-14B

### French ⇌ English

- legmlai/legml-v1.0-8b-instruct

### Nepali ⇌ English

- himalaya-ai/himalaya-gemma-4-e2b-it

### Indian Languages

- sarvamai/sarvam-translate

### Southeast Asian Languages

- aisingapore/Qwen-SEA-LION-v4-4B-VL
- aisingapore/Gemma-SEA-LION-v4.5-E2B-IT
- aisingapore/Qwen-SEA-LION-v4-8B-VL

### Basque / Galician / Catalan / Spanish / English

- HiTZ/Latxa-Qwen3-VL-4B-Instruct
- HiTZ/Latxa-Qwen3.5-4B

------

## Disclaimer

This list is not a formal benchmark. Model quality changes with prompts, sampling settings, quantization, backend, language pair, and content type. Always test models with your own translation samples before relying on them for serious work.


[^1]: Fine-tuned on English. The same applies below.
[^2]: Including `Assamese, Bengali, Bodo, Dogri, Gujarati, English, Hindi, Kannada, Kashmiri, Konkani, Maithili, Malayalam, Manipuri, Marathi, Nepali, Odia, Punjabi, Sanskrit, Santali, Sindhi, Tamil, Telugu, Urdu`
[^3]: This CoT is very long.
[^4]: Including `Burmese, Indonesian, Filipino, Malay, Tamil, Thai, and Vietnamese`
[^5]: Including `Basque, Galician, Catalan, Spanish, English` and more
[^6]: Gemma3n series (E2B/E4B) is optimized for CPU performance. Check [Gemma3n](https://ai.google.dev/gemma/docs/gemma-3n#parameters) for more details.
[^7]: 31 Ugandan languages `Acoli Adhola Alur Bari Chiga Gwere Kumam Karamojong Kakwa Kinyarwanda Konzo Kupsabiny Lango (Uganda) Lugbara Saamia Aringa Ganda Ma'di Masaaba Nyole Nyankole Nyoro Pokangá Gungu Ruuli Amba (Uganda); Swahili (macrolanguage); Teso Talinga-Bwisi Tooro Soga` + English
