# Local LLM Models Collection For Translation
This is only a small list of Collection for llm models under 14B which are used for translation.</br>
Depends on your languages/taste/usage/content, the results & performances **may or may not** meet your expectation.</br>

Most models below are finetune of 
- Qwen
  - [Qwen 3 1.7B/4B/8B/14B](https://huggingface.co/collections/Qwen/qwen3)
  - [QWEN 3VL 2B/4B/8B](https://huggingface.co/collections/Qwen/qwen3-vl)
- Gemma
  - [Gemma 3 4B/12B](https://huggingface.co/collections/google/gemma-3-release)
  - [Gemma 3n E2B/E4B](https://huggingface.co/collections/google/gemma-3n)
- Mistral
  - [Ministral 3B/8B/14B](https://huggingface.co/collections/mistralai/ministral-3)
  - [Mistral Nemo 12B](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407)

Explaination can be found here:
- [**FAQ-Frequent Ask Questions**](FAQ_EN.md)
  - [Models & Performance](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/FAQ_EN.md#models--performance)

## Must Read
Unless you had the knowledge.
- [LLM VRAM USAGE LISTS](OtherModels_gguf.md)
  - [**GGUF quantization types & relative quality**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)

- [**Deploy local models**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/README_en.md#deploying-local-models)

-----

### Highly Recommend to Read
- [**How to choose an LLM? Online vs Local**](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/OtherModels_gguf.md#gguf-quantization-types--relative-quality)
  - [Local models](https://github.com/CYBIRD-D/How-to-Choose-your-LLM-Model-for-translation/blob/main/README_en.md#local-models-open-weight--open-source)
- [**FAQ-Frequent Ask Questions**](FAQ_EN.md)


## Recommend models
Before check the list, you need to understand some basic knowledge.
- **How to read model names?** </br>
Example: **Qwen3-8B-Thinking-2507-abliterated-Q8_0-gguf** </br>
(This model name is hypothetical for illustration.)</br>

  - **Qwen3**: base model family
  - **8B**: parameter count. Common sizes: 4B±; 8B±; 14B±; 30B±; 70B±; 100B+
    - For VRAM & params, see [**LLM VRAM USAGE LISTS**](OtherModels_gguf.md)
      
  - **Thinking**: indicates a thinking-mode model (not all thinking models are labeled).
  
  - **2507**: time tag (2025/07), often minor updates.
  
  - **abliterated**: a way/style of “**de-safety-filtered**” fine-tune; typically means moderation is reduced or removed.
    - You’ll also see ***uncensored*/*NSFW*/*heretic*/*amoral*/*evil***, etc.
   
  - **Q8_0 (gguf)**: a llama.cpp quantization type. See the link:
    - [**LLM VRAM USAGE LISTS**](OtherModels_gguf.md) 
      - **GGUF Quantization types & relative quality**

-------
> Note: </br>
> 1. Quantizations since **Q5_K** and above usually no noticing quality loss.</br>
> 2. **Larger model size** × data × compute usually means better performance (the scaling law).
>     - For example: Qwen3-4B < Qwen3-8B < Qwen3-14B < Qwen3-32B
> 3. Translation quality also depends on the **quality & amount of training data** on certain languages. 

**Only download GGUF file** unless you're not using llama.cpp (that includes LM Studio, Ollama, Kobold, etc.)

### 0~3B (Vram≤4GB)
LLMs at this scale usually have poor performance.</br>
All links are from Hugging Face.</br>
All models are choosen based on **community reports, downloads, likes and finetune languages**.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| shisa-ai/shisa-v2.1-lfm2-1.2b </br> shisa-ai/shisa-v2.1-llama3.2-3b                         | **JP⇌EN** | LFM2 </br> Llama3.2 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-lfm2-1.2b-GGUF) </br> [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-llama3.2-3b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-lfm2-1.2b) </br> [Original](https://huggingface.co/shisa-ai/shisa-v2.1-llama3.2-3b) |
| tencent/HY-MT1.5-1.8B                             | General | HY-MT1.5 | [GGUF](https://huggingface.co/mradermacher/HY-MT1.5-1.8B-GGUF) | [Original](https://huggingface.co/tencent/HY-MT1.5-1.8B) |
| Unbabel/Tower-Plus-2B                             | General | Gemma2 | [GGUF](https://huggingface.co/DZgas/Tower-Plus-2B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-2B) |
| prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1 | **EN**⇌XX [^1] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-2B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-2B-Instruct-abliterated-v1) |
| Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1  | General | Qwen3 | [GGUF](mradermacher/Josiefied-Qwen3-1.7B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-1.7B-abliterated-v1) |
| mistralai/Ministral-3-3B-Instruct-2512  | General | Mistral3 | [GGUF](https://huggingface.co/unsloth/Ministral-3-3B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-3B-Instruct-2512) |
| tiiuae/Falcon-H1-1.5B-Deep-Instruct </br> tiiuae/Falcon-H1-3B-Instruct  | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-1.5B-Deep-Instruct-GGUF) </br> [GGUF](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct-GGUF) | [Original](tiiuae/Falcon-H1-1.5B-Deep-Instruct) </br> [Original](https://huggingface.co/tiiuae/Falcon-H1-3B-Instruct) |


[^1]: Finetune on ENG. The same applies below.

---------

### 4B/5B (Vram≈4GB~6GB)

> **`★` means model has been tested on some languages/tasks**.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| sarvamai/sarvam-translate  （note:4B） | **22 official Indian languages**[^2] | Gemma3 | [GGUF](https://huggingface.co/mradermacher/sarvam-translate-GGUF) | [Original](https://huggingface.co/sarvamai/sarvam-translate) |  
| INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0 | **Ukrainian⇌EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-4B-IT-v1.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-4B-IT-v1.0) | 
| **★mlabonne/gemma-3-4b-it-abliterated-v2**       | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-4b-it-abliterated-v2-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-4b-it-abliterated-v2) | 
| **★Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-4B-Instruct-2507-gabliterated-v2) | 
| RefalMachine/RuadaptQwen3-4B-Instruct | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct-GGUF) | [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-4B-Instruct) | 
| **★SakuraLLM/GalTransl-v4-4B-2512** | **JP⇌CN** | Qwen3 | [GGUF](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2512) | [Original](https://huggingface.co/SakuraLLM/GalTransl-v4-4B-2512) | 
| ★DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored (***[!]long thinking***[^3]) | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored-GGUF) | [Original](https://huggingface.co/DavidAU/Qwen3-4B-2507-Thinking-heretic-abliterated-uncensored) | .
| prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1 | **EN**⇌XX | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-4B-Instruct-abliterated-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-4B-Instruct-abliterated-v1) | 
| aisingapore/Qwen-SEA-LION-v4-4B-VL | **ENG+7key SEA languages**[^4] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-4B-VL-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-4B-VL) |  
| HiTZ/Latxa-Qwen3-VL-4B-Instruct | **5+**[^5] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Latxa-Qwen3-VL-4B-Instruct-GGUF) | [Original](https://huggingface.co/HiTZ/Latxa-Qwen3-VL-4B-Instruct) | 
| MuXodious/gemma-3n-E2B-it-absolute-heresy （5B/**CPU-optimized**)[^6]  | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E2B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E2B-it-absolute-heresy) |  

[^2]: Including `Assamese, Bengali, Bodo, Dogri, Gujarati, English, Hindi, Kannada, Kashmiri, Konkani, Maithili, Malayalam, Manipuri, Marathi, Nepali, Odia, Punjabi, Sanskrit, Santali, Sindhi, Tamil, Telugu, Urdu`
[^3]: This CoT is very long.
[^4]: Including `Burmese, Indonesian, Filipino, Malay, Tamil, Thai, and Vietnamese`
[^5]: Including `Basque, Galician, Catalan, Spanish, English` and more
[^6]: Gemma3n series (E2B/E4B) is optimized for CPU performance. Check [Gemma3n](https://ai.google.dev/gemma/docs/gemma-3n#parameters) for more details.

-------

### 7B-10B (Vram≈6G~8G)
New LLMs at this size ususally have a decent quality of translation.

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| ★tiiuae/Falcon-H1-7B-Instruct </br>  | General | FalconH1 | [GGUF](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct-GGUF) | [Original](https://huggingface.co/tiiuae/Falcon-H1-7B-Instruct) |  
| ★MuXodious/gemma-3n-E4B-it-absolute-heresy (7B/CPU-optimized) | General | Gemma3n | [GGUF](https://huggingface.co/mradermacher/gemma-3n-E4B-it-absolute-heresy-GGUF) | [Original](https://huggingface.co/MuXodious/gemma-3n-E4B-it-absolute-heresy) |  
| **★Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1**| General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-8B-abliterated-v1-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-8B-abliterated-v1) |  
| **★mlabonne/Qwen3-8B-abliterated** | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-8B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-8B-abliterated) |  
| AvitoTech/avibe  (8B)</br> t-tech/T-lite-it-2.1  (8B)</br>RefalMachine/RuadaptQwen3-8B-Hybrid | **Russian⇌EN** | Qwen3 | [GGUF](https://huggingface.co/NightForger/avibe-GGUF)</br> [GGUF](https://huggingface.co/t-tech/T-lite-it-2.1-GGUF) </br> [GGUF](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid-GGUF) | [Original](https://huggingface.co/AvitoTech/avibe) </br> [Original](https://huggingface.co/t-tech/T-lite-it-2.1) </br> [Original](https://huggingface.co/RefalMachine/RuadaptQwen3-8B-Hybrid) |  
| legmlai/legml-v1.0-8b-instruct | **French⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/legml-v1.0-8b-instruct-GGUF) | [Original](https://huggingface.co/legmlai/legml-v1.0-8b-instruct) |  
| **★shisa-ai/shisa-v2.1-qwen3-8b** | **JP⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/shisa-v2.1-qwen3-8b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2.1-qwen3-8b) |  
| **★prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2** | **EN**⇌XX | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen3-VL-8B-Instruct-abliterated-v2.0-GGUF) | [Original](https://huggingface.co/prithivMLmods/Qwen3-VL-8B-Instruct-abliterated-v2) | 
| aisingapore/Qwen-SEA-LION-v4-8B-VL | **ENG+7key SEA languages**[^4] | Qwen3VL | [GGUF](https://huggingface.co/mradermacher/Qwen-SEA-LION-v4-8B-VL-GGUF) | [Original](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-8B-VL) | 
| **★SakuraLLM/Sakura-GalTransl-7B-v3.7** | **JP⇌CHINESE** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-7B-v3.7) |  
| **★mistralai/Ministral-3-8B-Instruct-2512** | General | Ministral3 | [GGUF](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-8B-Instruct-2512) | 
| **★Unbabel/Tower-Plus-9B** | General | Gemma2 | [GGUF](https://huggingface.co/mradermacher/Tower-Plus-9B-GGUF) | [Original](https://huggingface.co/Unbabel/Tower-Plus-9B) |
| KORMo-Team/KORMo-10B-sft | **Korean⇌EN** | KORMo | [GGUF](https://huggingface.co/mradermacher/KORMo-10B-sft-GGUF) | [Original](https://huggingface.co/KORMo-Team/KORMo-10B-sft) |

----------


### 12B-14B (Vram≈12G~16G)

| Model Name | Languages | Base Model Family | Link(GGUF) | Link(Original Page) |
|---|---:|---:|---:|---:|
| **★Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3**  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Josiefied-Qwen3-14B-abliterated-v3-GGUF) | [Original](https://huggingface.co/Goekdeniz-Guelmez/Josiefied-Qwen3-14B-abliterated-v3) |  
| **★mlabonne/Qwen3-14B-abliterated**  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Qwen3-14B-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/Qwen3-14B-abliterated) |  
| NousResearch/Hermes-4-14B  | General | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Hermes-4-14B-GGUF) | [Original](https://huggingface.co/NousResearch/Hermes-4-14B) |  
| Sunbird/Sunflower-14B | **Ugandan[^7]⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/Sunbird/Sunflower-14B) |  
| suayptalha/Sungur-14B | **Turkish⇌EN** | Qwen3 | [GGUF](https://huggingface.co/mradermacher/Sungur-14B-GGUF) | [Original](https://huggingface.co/Sunbird/Sunflower-14B) | 
| sugoitoolkit/Sugoi-14B-Ultra-HF | **JP⇌EN** | Qwen2.5 | [GGUF](https://huggingface.co/mradermacher/Sugoi-14B-Ultra-HF-GGUF) | [Original](https://huggingface.co/sugoitoolkit/Sugoi-14B-Ultra-HF) |
| ★SakuraLLM/Sakura-GalTransl-14B-v3.8 | **JP⇌CHINESE** | Qwen2.5 | [GGUF](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) | [Original](https://huggingface.co/SakuraLLM/Sakura-GalTransl-14B-v3.8) |
| INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0 | **Ukrainian⇌EN** | Gemma3 | [GGUF](https://huggingface.co/mradermacher/MamayLM-Gemma-3-12B-IT-v1.0-GGUF) | [Original](https://huggingface.co/INSAIT-Institute/MamayLM-Gemma-3-12B-IT-v1.0) |
| **★mlabonne/gemma-3-12b-it-abliterated-v2** </br> mlabonne/gemma-3-12b-it-qat-abliterated | General | Gemma3 | [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-abliterated-v2-GGUF) </br> [GGUF](https://huggingface.co/mradermacher/gemma-3-12b-it-qat-abliterated-GGUF) | [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-abliterated-v2) </br> [Original](https://huggingface.co/mlabonne/gemma-3-12b-it-qat-abliterated) |
| ★mistralai/Ministral-3-14B-Instruct-2512 | General | Ministral | [GGUF](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512-GGUF) | [Original](https://huggingface.co/mistralai/Ministral-3-14B-Instruct-2512) |
| jenerallee78/Ministral-3-14B-abliterated | General | Ministral | [GGUF](https://huggingface.co/mradermacher/Ministral-3-14B-abliterated-GGUF) | [Original](https://huggingface.co/jenerallee78/Ministral-3-14B-abliterated) |
| mistralai/Mistral-Nemo-Instruct-2407 | General | Mistralnemo | [GGUF](https://huggingface.co/MaziyarPanahi/Mistral-Nemo-Instruct-2407-GGUF) | [Original](Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24) |
| Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24 | **Russian⇌EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/Vikhr-Nemo-12B-Instruct-R-21-09-24-GGUF) | [Original](Vikhrmodels/Vikhr-Nemo-12B-Instruct-R-21-09-24) |
| shisa-ai/shisa-v2-mistral-nemo-12b | **JP⇌EN** | Mistralnemo | [GGUF](https://huggingface.co/mradermacher/shisa-v2-mistral-nemo-12b-GGUF) | [Original](https://huggingface.co/shisa-ai/shisa-v2-mistral-nemo-12b) |


[^7]: 31 Ugandan languages `Acoli Adhola Alur Bari Chiga Gwere Kumam Karamojong Kakwa Kinyarwanda Konzo Kupsabiny Lango (Uganda) Lugbara Saamia Aringa Ganda Ma'di Masaaba Nyole Nyankole Nyoro Pokangá Gungu Ruuli Amba (Uganda); Swahili (macrolanguage); Teso Talinga-Bwisi Tooro Soga` + English
