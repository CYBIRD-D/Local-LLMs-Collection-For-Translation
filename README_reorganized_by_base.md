# Local LLMs Collection For Translation
This is only a **small list** of Collection for llms under 14B which are used for translation.</br>
Depends on your languages/taste/usage/content, the results & performances **may or may not** meet your expectation.</br>

Explaination can be found here:
- [Models & Performance](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/FAQ_EN.md#models--performance)

<details>
 <summary>   
Most models below are finetune of Qwen/Gemma/Mistral 

</summary>

- Qwen
  - [Qwen 3 1.7B/4B/8B/14B](https://huggingface.co/collections/Qwen/qwen3)
  - [QWEN 3VL 2B/4B/8B](https://huggingface.co/collections/Qwen/qwen3-vl)
- Gemma
  - [Gemma 3 4B/12B](https://huggingface.co/collections/google/gemma-3-release)
  - [Gemma 3n E2B/E4B](https://huggingface.co/collections/google/gemma-3n)
- Mistral
  - [Ministral 3B/8B/14B](https://huggingface.co/collections/mistralai/ministral-3)
  - [Mistral Nemo 12B](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407)

</details>

## Must Read
Unless you had the knowledge.
- [LLM VRAM USAGE LISTS](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md)
  - [**GGUF quantization types & relative quality**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)

- [**Deploy local models**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/tree/main#deploying-local-models)

-----

<details>
 <summary>   
   
### Highly Recommend to Read
</summary>

- [**How to choose an LLM? Online vs Local**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)
  - [Local models](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/README_en.md#local-models-open-weight--open-source)
- [**FAQ-Frequent Ask Questions**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/FAQ_EN.md)
- [**【★】Free LLM API Providers**](https://github.com/CYBIRD-D/FREE-LLM-API-Provider)

</details>

## Recommend models
Before check the list, you need to understand some basic knowledge.
<details>
 <summary>   

### **How to read model names?** </br>
Example: **Qwen3-8B-Thinking-2507-abliterated-Q8_0-gguf**
</summary>
(This model name is hypothetical for illustration.)</br>

  - **Qwen3**: base model family
  - **8B**: parameter count. Common sizes: 4B±; 8B±; 14B±; 30B±; 70B±; 100B+
    - For VRAM & params, see [**LLM VRAM USAGE LISTS**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md)
      
  - **Thinking**: indicates a thinking-mode model (not all thinking models are labeled).
  
  - **2507**: time tag (2025/07), often some updates.
  
  - **abliterated**: a way/style of “**de-safety-filtered**” fine-tune; typically means moderation is reduced or removed.
    - You’ll also see ***uncensored*/*NSFW*/*heretic*/*amoral*/*evil***, etc.
   
  - **Q8_0 (gguf)**: a llama.cpp quantization type. See the link:
    - [**GGUF quantization types & relative quality**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)

</details>

-------
> **Note**: </br>
> 1. Quantizations since **`Q5_K`** and above usually no noticing quality loss.</br>
> 2. **Larger model size** × data × compute usually means better performance (the scaling law).
>     - For example: Qwen3-4B < Qwen3-8B < Qwen3-14B < Qwen3-32B
> 3. Translation quality also depends on the **quality & amount of training data** on certain languages. 

**Only download GGUF file** unless you're not using llama.cpp (that includes LM Studio, Ollama, Kobold, etc.) </br>
For Mac with Apple silicon (M series) check here [LM Studio with Apple MLX](https://lmstudio.ai/blog/lmstudio-v0.3.4)

### VRAM tiers / marks

LLMs at 0~3B scale usually have poor performance.</br>
All links are from Hugging Face.</br>
All models are choosen based on **community reports, downloads, likes and finetune languages**.

> **`★` means model has been tested on some languages/tasks**.
>
> New LLMs at 7B-10B size ususally have a decent quality of translation.

| VRAM Tier | Required VRAM | Note |
|---|---:|---|
| 0~3B | Vram≤4GB | Usually poor performance |
| 4B/5B | Vram≈4GB~6GB | Small local models |
| 7B-10B | Vram≈6G~8G | Usually decent translation quality |
| 12B-14B | Vram≈12G~16G | Larger local models under 14B± |

### Models by vendor / base model family

Each base model family is grouped in a collapsible section. Inside each section, models are sorted by required VRAM from small to large.

<details>
<summary><strong>LiquidAI / LFM2</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | shisa-ai/shisa-v2.1-lfm2-1.2b | **JP⇌EN** | LFM2 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-lfm2-1.2b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-lfm2-1.2b) |

</details>

<details>
<summary><strong>Meta / Llama3.2</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | shisa-ai/shisa-v2.1-llama3.2-3b | **JP⇌EN** | Llama3.2 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-llama3.2-3b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-llama3.2-3b) |

</details>

<details>
<summary><strong>LiquidAI / LFM2.5</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | LiquidAI/LFM2.5-1.2B-JP | **JP⇌EN** | LFM2.5 | [GGUF](https://huggingface.co/LiquidAI/LFM2.5-1.2B-JP-GGUF) | [Original](https://huggingface.co/LiquidAI/LFM2.5-1.2B-JP) |

</details>

<details>
<summary><strong>LGAI-EXAONE / EXAONE4.0</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | LGAI-EXAONE/EXAONE-4.0-1.2B | **Spanish⇌EN⇌Korean** | EXAONE4.0 | [GGUF](https://huggingface.co/LGAI-EXAONE/EXAONE-4.0-1.2B-GGUF) | [Original](https://huggingface.co/LGAI-EXAONE/EXAONE-4.0-1.2B) |

</details>

<details>
<summary><strong>Tencent / HY-MT1.5</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | tencent/HY-MT1.5-1.8B | General | HY-MT1.5 | [GGUF](https://huggingface.co/mradermacher/HY-MT1.5-1.8B-GGUF) | [Original](https://huggingface.co/tencent/HY-MT1.5-1.8B) |

</details>

<details>
<summary><strong>Google / Gemma2</strong> — 2 model(s), Vram≤4GB → Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | Unbabel/Tower-Plus-2B | General | Gemma2 | [GGUF](https://huggingface.co/DZgas/Tower-Plus-2B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-2B) |
| Vram≈6G~8G | ★ | **★Unbabel/Tower-Plus-9B** | General | Gemma2 | [GGUF](https://huggingface.co/mradermacher/Tower-Plus-9B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-9B) |

</details>

<details>
<summary><strong>Qwen / Qwen3VL</strong> — 6 model(s), Vram≤4GB → Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1 | **EN**⇌XX [^1] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-2B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1) |
| Vram≈4GB~6GB |  | prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1 | **EN**⇌XX | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-4B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1) |
| Vram≈4GB~6GB |  | aisingapore/Qwen-SEA-LION-v4-4B-VL | **ENG+7key SEA languages**[^4] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-4B-VL-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-4B-VL) |
| Vram≈4GB~6GB |  | HiTZ/Latxa-Qwen3-VL-4B-Instruct | **5+**[^5] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Latxa-Qwen3-VL-4B-Instruct-GGUF) | [Original](https://huggingface.co/HiTZ/Latxa-Qwen3-VL-4B-Instruct) |
| Vram≈6G~8G | ★ | **★prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2** | **EN**⇌XX | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-8B-Instruct-abliterated-v2.0-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2) |
| Vram≈6G~8G |  | aisingapore/Qwen-SEA-LION-v4-8B-VL | **ENG+7key SEA languages**[^4] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-8B-VL-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-8B-VL) |

</details>

<details>
<summary><strong>Qwen / Qwen3</strong> — 17 model(s), Vram≤4GB → Vram≈12G~16G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1 | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-1.7B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1) |
| Vram≈4GB~6GB | ★ | ★Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2 | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2) |
| Vram≈4GB~6GB |  | RefalMachine/RuadaptQwen3-4B-Instruct | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct-GGUF) | [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct) |
| Vram≈4GB~6GB | ★ | **★SakuraLLM/GalTransl-v4-4B-2601** | **JP⇌CN** | Qwen3 | [GGUF](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2601) | [Original](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2601) |
| Vram≈4GB~6GB | ★ | ★DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored (***[!]long thinking***[^3]) | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored-GGUF) | [Original](https://huggingface.co/DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored) . |
| Vram≈6G~8G | ★ | **★Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-8B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1) |
| Vram≈6G~8G | ★ | **★mlabonne/Qwen3-8B-abliterated** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-8B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-8B-abliterated) |
| Vram≈6G~8G |  | AvitoTech/avibe  (8B) | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/NightForger/avibe-GGUF) | [Original](https://huggingface.co/AvitoTech/avibe) |
| Vram≈6G~8G |  | t-tech/T-lite-it-2.1  (8B) | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/t-tech/T-lite-it-2.1-GGUF) | [Original](https://huggingface.co/t-tech/T-lite-it-2.1) |
| Vram≈6G~8G |  | RefalMachine/RuadaptQwen3-8B-Hybrid | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid-GGUF) | [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid) |
| Vram≈6G~8G |  | legmlai/legml-v1.0-8b-instruct | **French⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/legml-v1.0-8b-instruct-GGUF) | [Original](https://huggingface.co/legmlai/legml-v1.0-8b-instruct) |
| Vram≈6G~8G | ★ | **★shisa-ai/shisa-v2.1-qwen3-8b** | **JP⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-qwen3-8b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-qwen3-8b) |
| Vram≈12G~16G | ★ | **★Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-14B-abliterated-v3-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3) |
| Vram≈12G~16G | ★ | **★mlabonne/Qwen3-14B-abliterated** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-14B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-14B-abliterated) |
| Vram≈12G~16G |  | NousResearch/Hermes-4-14B | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Hermes-4-14B-GGUF) | [Original](https://huggingface.co/NousResearch/Hermes-4-14B) |
| Vram≈12G~16G |  | Sunbird/Sunflower-14B | **Ugandan[^7]⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/Sunbird/Sunflower-14B) |
| Vram≈12G~16G |  | suayptalha/Sungur-14B | **Turkish⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/Sunbird/Sunflower-14B) |

</details>

<details>
<summary><strong>Mistral AI / Ministral-3</strong> — 4 model(s), Vram≤4GB → Vram≈12G~16G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | mistralai/Ministral-3-3B-Instruct-2512 | General | Mistral3 | [GGUF](https://huggingface.co/unsloth/Ministral-3-3B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-3B-Instruct-2512) |
| Vram≈6G~8G | ★ | **★mistralai/Ministral-3-8B-Instruct-2512** | General | Ministral3 | [GGUF](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512) |
| Vram≈12G~16G | ★ | ★mistralai/Ministral-3-14B-Instruct-2512 | General | Ministral | [GGUF](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512) |
| Vram≈12G~16G |  | jenerallee78/Ministral-3-14B-abliterated | General | Ministral | [GGUF](https://huggingface.co/mradermacher/Ministral-3-14B-abliterated-GGUF) | [Original](https://huggingface.co/jenerallee78/Ministral-3-14B-abliterated) |

</details>

<details>
<summary><strong>TII UAE / FalconH1</strong> — 3 model(s), Vram≤4GB → Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | tiiuae/Falcon-H1-1.5B-Deep-Instruct | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-1.5B-Deep-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-1.5B-Deep-Instruct) |
| Vram≤4GB |  | tiiuae/Falcon-H1-3B-Instruct | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct) |
| Vram≈6G~8G | ★ | ★tiiuae/Falcon-H1-7B-Instruct | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct) |

</details>

<details>
<summary><strong>Cohere / aya</strong> — 1 model(s), Vram≤4GB</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≤4GB |  | CohereLabs/tiny-aya series (3b) | General | aya | Samelink | [Original Collection](https://huggingface.co/collections/CohereLabs/tiny-aya) |

</details>

<details>
<summary><strong>Google / Gemma3</strong> — 8 model(s), Vram≈4GB~6GB → Vram≈12G~16G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈4GB~6GB |  | sarvamai/sarvam-translate  （note:4B） | **22 official Indian languages**[^2] | Gemma3 | [GGUF](https://huggingface.co/mradermacher/sarvam-translate-GGUF) | [Original](https://huggingface.co/sarvamai/sarvam-translate) |
| Vram≈4GB~6GB |  | INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0 | **Ukrainian⇌EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-4B-IT-v1.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0) |
| Vram≈4GB~6GB | ★ | **★google/translategemma-4b-it** | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/translategemma-4b-it-GGUF) | [Original](https://huggingface.co/google/translategemma-4b-it) |
| Vram≈4GB~6GB | ★ | ★mlabonne/gemma-3-4b-it-abliterated-v2 | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-4b-it-abliterated-v2-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-4b-it-abliterated-v2) |
| Vram≈12G~16G | ★ | **★google/translategemma-12b-it** | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/translategemma-12b-it-GGUF) | [Original](https://huggingface.co/google/translategemma-12b-it) |
| Vram≈12G~16G |  | INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0 | **Ukrainian⇌EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-12B-IT-v1.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0) |
| Vram≈12G~16G | ★ | **★mlabonne/gemma-3-12b-it-abliterated-v2** | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-abliterated-v2-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-abliterated-v2) |
| Vram≈12G~16G |  | mlabonne/gemma-3-12b-it-qat-abliterated | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-qat-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-qat-abliterated) |

</details>

<details>
<summary><strong>Google / Gemma3n</strong> — 2 model(s), Vram≈4GB~6GB → Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈4GB~6GB |  | MuXodious/gemma-3n-E2B-it-absolute-heresy （5B/**CPU-optimized**)[^6] | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E2B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E2B-it-absolute-heresy) |
| Vram≈6G~8G | ★ | ★MuXodious/gemma-3n-E4B-it-absolute-heresy (7B/CPU-optimized) | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E4B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E4B-it-absolute-heresy) |

</details>

<details>
<summary><strong>Google / Gemma4</strong> — 1 model(s), Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G | ★ | ★google/gemma-4-E4B-it （8B/**CPU-optimized**) | General | Gemma4 | [GGUF](https://huggingface.co/unsloth/gemma-4-E4B-it-GGUF) | [Original](https://huggingface.co/google/gemma-4-E4B-it) |

</details>

<details>
<summary><strong>NVIDIA / Nemotron 2 Nano</strong> — 1 model(s), Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G |  | nvidia/NVIDIA-Nemotron-Nano-9B-v2-Japanese | **JP⇌EN** | Nemotron 2 Nano | [GGUF](https://huggingface.co/mmnga-o/NVIDIA-Nemotron-Nano-9B-v2-Japanese-gguf) | [Original](https://huggingface.co/nvidia/NVIDIA-Nemotron-Nano-9B-v2-Japanese) |

</details>

<details>
<summary><strong>Qwen / Qwen2.5</strong> — 4 model(s), Vram≈6G~8G → Vram≈12G~16G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G | ★ | **★SakuraLLM/Sakura-GalTransl-7B-v3.7** | **JP⇌CHINESE** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) |
| Vram≈6G~8G |  | skt/A.X-4.0-Light | **Korean⇌EN** | Qwen2.5 | [GGUF](https://huggingface.co/mykor/A.X-4.0-Light-gguf) | [Original](https://github.com/SKT-AI/A.X-4.0/tree/main) |
| Vram≈12G~16G |  | sugoitoolkit/Sugoi-14B-Ultra-HF | **JP⇌EN** | Qwen2.5 | [GGUF](https://huggingface.co/mradermacher/Sugoi-14B-Ultra-HF-GGUF) | [Original](https://huggingface.co/sugoitoolkit/Sugoi-14B-Ultra-HF) |
| Vram≈12G~16G | ★ | ★SakuraLLM/Sakura-GalTransl-14B-v3.8 | **JP⇌CHINESE** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) |

</details>

<details>
<summary><strong>Cohere / aya23</strong> — 1 model(s), Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G |  | lenML/aya-expanse-8b-abliterated | General | aya23 | [GGUF](https://huggingface.co/mradermacher/aya-expanse-8b-abliterated-GGUF) | [Original](https://huggingface.co/lenML/aya-expanse-8b-abliterated) |

</details>

<details>
<summary><strong>KORMo-Team / KORMo</strong> — 1 model(s), Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G |  | KORMo-Team/KORMo-10B-sft | **Korean⇌EN** | KORMo | [GGUF](https://huggingface.co/mradermacher/KORMo-10B-sft-GGUF) | [Original](https://huggingface.co/KORMo-Team/KORMo-10B-sft) |

</details>

<details>
<summary><strong>LGAI-EXAONE / EXAONE-3.5</strong> — 1 model(s), Vram≈6G~8G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈6G~8G |  | LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct | **Korean⇌EN** | EXAONE-3.5 | [GGUF](https://huggingface.co/mradermacher/EXAONE-3.5-7.8B-Instruct-GGUF) | [Original](https://huggingface.co/LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct) |

</details>

<details>
<summary><strong>Mistral AI / Mistralnemo</strong> — 3 model(s), Vram≈12G~16G</summary>

| Required VRAM | Mark | Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---|---:|---:|---:|---:|
| Vram≈12G~16G |  | mistralai/Mistral-Nemo-Instruct-2407 | General | Mistralnemo | [GGUF](https://huggingface.co/MaziyarPanahi/Mistral-Nemo-Instruct-2407-GGUF) | [Original](Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24) |
| Vram≈12G~16G |  | Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24 | **Russian⇌EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/Vikhr-Nemo-12B-Instruct-R-21-09-24-GGUF) | [Original](Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24) |
| Vram≈12G~16G | ★ | **★shisa-ai/shisa-v2-mistral-nemo-12b** | **JP⇌EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/shisa-v2-mistral-nemo-12b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2-mistral-nemo-12b) |

</details>

[^1]: Finetune on ENG. The same applies below.

[^2]: Including `Assamese, Bengali, Bodo, Dogri, Gujarati, English, Hindi, Kannada, Kashmiri, Konkani, Maithili, Malayalam, Manipuri, Marathi, Nepali, Odia, Punjabi, Sanskrit, Santali, Sindhi, Tamil, Telugu, Urdu`
[^3]: This CoT is very long.
[^4]: Including `Burmese, Indonesian, Filipino, Malay, Tamil, Thai, and Vietnamese`
[^5]: Including `Basque, Galician, Catalan, Spanish, English` and more
[^6]: Gemma3n series (E2B/E4B) is optimized for CPU performance. Check [Gemma3n](https://ai.google.dev/gemma/docs/gemma-3n#parameters) for more details.
[^7]: 31 Ugandan languages `Acoli Adhola Alur Bari Chiga Gwere Kumam Karamojong Kakwa Kinyarwanda Konzo Kupsabiny Lango (Uganda) Lugbara Saamia Aringa Ganda Ma'di Masaaba Nyole Nyankole Nyoro Pokangá Gungu Ruuli Amba (Uganda); Swahili (macrolanguage); Teso Talinga-Bwisi Tooro Soga` + English
