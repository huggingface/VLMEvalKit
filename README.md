![LOGO](http://opencompass.openxlab.space/utils/MMLB.jpg)
<div align="center"><b>A Toolkit for Evaluating Large Vision-Language Models. </b></div>

<div align="center">
<a href="https://rank.opencompass.org.cn/leaderboard-multimodal">🏆 Learderboard </a> •
<a href="#-datasets-models-and-evaluation-results">📊Datasets & Models </a> •
<a href="#%EF%B8%8F-quickstart">🏗️Quickstart </a> •
<a href="#%EF%B8%8F-development-guide">🛠️Development </a> •
<a href="#-the-goal-of-vlmevalkit">🎯Goal </a> •
<a href="#%EF%B8%8F-citation">🖊️Citation </a>
</div>

<div align="center">
<a href="https://huggingface.co/spaces/opencompass/open_vlm_leaderboard">🤗 Leaderboard on HuggingFace</a>
<a href="https://openxlab.org.cn/apps/detail/kennyutc/open_mllm_leaderboard">🤖 Leaderboard on OpenXlab</a>
</div>


**VLMEvalKit** (the python package name is **vlmeval**) is an **open-source evaluation toolkit** of **large vision-language models (LVLMs)**. It enables **one-command evaluation** of LVLMs on various benchmarks, without the heavy workload of data preparation under multiple repositories. In VLMEvalKit, we adopt **generation-based evaluation** for all LVLMs (obtain the answer via `generate` / `chat`  interface), and provide the evaluation results obtained with both **exact matching** and **LLM-based answer extraction**.

## 🆕 News

- **[2024-03-28]** Now you can use local OpenSource LLMs as the answer extractor or judge (see [**#132**](https://github.com/open-compass/VLMEvalKit/pull/132) for details). Great thanks to [**StarCycle**](https://github.com/StarCycle) 🔥🔥🔥
- **[2024-03-22]** We have supported [**LLaVA-NeXT**](https://llava-vl.github.io/blog/2024-01-30-llava-next/) 🔥🔥🔥
- **[2024-03-21]** We have supported [**DeepSeek-VL**](https://github.com/deepseek-ai/DeepSeek-VL/tree/main) 🔥🔥🔥
- **[2024-03-20]** We have supported users to use a `.env` file to manage all environment variables used in VLMEvalKit, see [**Quickstart**](\Quickstart.md) for more details
- **[2024-03-17]** We have added an API wrapper for [**Step-1V**](https://www.stepfun.com/#step1v) 🔥🔥🔥
- **[2024-03-15]** We have updated the LLaVA class be compatible with the latest version of LLaVA. All LLaVA series models have been re-evaluated with temperature=0, and the new results have been updated to the leaderboard 🔥🔥🔥
- **[2024-02-27]** We have fixed the evaluation results of [**Yi-VL-34B**](https://huggingface.co/01-ai/Yi-VL-34B), check the updated results [**here**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard)  🔥🔥🔥
- **[2024-02-25]** We have supported [**OCRBench**](https://github.com/Yuliang-Liu/MultimodalOCR)🔥🔥🔥
- **[2024-02-24]** We have supported [**InternVL-Chat Series**](https://github.com/OpenGVLab/InternVL). The models achieve over 80% Top-1 accuracies on MMBench v1.0 [[**Blog**](https://github.com/OpenGVLab/InternVL/blob/main/BLOG.md)] 🔥🔥🔥
- **[2024-02-07]** We have supported two new models: [**MiniCPM-V**](https://huggingface.co/openbmb/MiniCPM-V) and [**OmniLMM-12B**](https://huggingface.co/openbmb/OmniLMM-12B) 🔥🔥🔥


## 📊 Datasets, Models, and Evaluation Results

**The performance numbers on our official multi-modal leaderboards can be downloaded from here!**

[**OpenCompass Multi-Modal Leaderboard**](https://rank.opencompass.org.cn/leaderboard-multimodal): [Download All DETAILED Results](http://opencompass.openxlab.space/utils/OpenVLM.json).

**Supported Dataset**

| Dataset                                                      | Dataset Names (for run.py)                             | Task | Inference | Evaluation | Results                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------ | --------- | ---------- | ------------------------------------------------------------ |-----|
| [**MMBench Series**](https://github.com/open-compass/mmbench/): <br>MMBench, MMBench-CN, CCBench | MMBench-DEV-[EN/CN]<br>MMBench-TEST-[EN/CN]<br>CCBench | Multi-choice | ✅         | ✅          | [**MMBench Leaderboard**](https://mmbench.opencompass.org.cn/leaderboard) |
| [**MME**](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Evaluation) | MME | Yes or No                                                   | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**SEEDBench_IMG**](https://github.com/AILab-CVC/SEED-Bench) | SEEDBench_IMG | Multi-choice                                         | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**MM-Vet**](https://github.com/yuweihao/MM-Vet)             | MMVet  | VQA                                              | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**MMMU**](https://mmmu-benchmark.github.io)                 | MMMU_DEV_VAL/MMMU_TEST | Multi-choice                                | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**MathVista**](https://mathvista.github.io)                 | MathVista_MINI | VQA                                         | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**ScienceQA_IMG**](https://scienceqa.github.io)             | ScienceQA_[VAL/TEST] | Multi-choice                                   | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**COCO Caption**](https://cocodataset.org)                  | COCO_VAL | Caption                                              | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**HallusionBench**](https://github.com/tianyi-lab/HallusionBench) | HallusionBench | Yes or No                                         | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**OCRVQA**](https://ocr-vqa.github.io)                      | OCRVQA_[TESTCORE/TEST] | VQA                                 | ✅         | ✅          | **TBD.**                                                     |
| [**TextVQA**](https://textvqa.org)                           | TextVQA_VAL | VQA                                           | ✅         | ✅          | **TBD.**                                                     |
| [**ChartQA**](https://github.com/vis-nlp/ChartQA)            | ChartQA_TEST | VQA                                          | ✅         | ✅          | **TBD.**                                                     |
| [**AI2D**](https://allenai.org/data/diagrams)                | AI2D_TEST | Multi-choice                                             | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**LLaVABench**](https://huggingface.co/datasets/liuhaotian/llava-bench-in-the-wild) | LLaVABench | VQA                                            | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**DocVQA**](https://www.docvqa.org)                         | DocVQA_VAL | VQA                                            | ✅         | ✅          | **TBD.**                                                     |
| [**OCRBench**](https://github.com/Yuliang-Liu/MultimodalOCR) | OCRBench | VQA                                              | ✅         | ✅          | [**Open_VLM_Leaderboard**](https://huggingface.co/spaces/opencompass/open_vlm_leaderboard) |
| [**Core-MM**](https://github.com/core-mm/core-mm)            | CORE_MM | VQA                                               | ✅         |            | **N/A**                                                      |

VLMEvalKit will use an **judge LLM** to extract answer from the output if you set the key, otherwise it uses the **exact matching** mode (find "Yes", "No", "A", "B", "C"... in the output strings). **The exact matching can only be applied to the Yes-or-No tasks and the Multi-choice tasks.**

**There are some known issues with VQA tasks like OCRVQA, TextVQA, ChartQA, etc. We will fix them asap.**

**Supported API Models**

| [**GPT-4-Vision-Preview**](https://platform.openai.com/docs/guides/vision)🎞️🚅 | [**GeminiProVision**](https://platform.openai.com/docs/guides/vision)🎞️🚅 | [**QwenVLPlus**](https://huggingface.co/spaces/Qwen/Qwen-VL-Plus)🎞️🚅 | [**QwenVLMax**](https://huggingface.co/spaces/Qwen/Qwen-VL-Max)🎞️🚅 | [**Step-1V**](https://www.stepfun.com/#step1v)🎞️🚅 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------ |

**Supported PyTorch / HF Models**

| [**IDEFICS-[9B/80B]-Instruct**](https://huggingface.co/HuggingFaceM4/idefics-9b-instruct)🎞️🚅 | [**InstructBLIP-[7B/13B]**](https://github.com/salesforce/LAVIS/blob/main/projects/instructblip/README.md) | [**LLaVA-[v1-7B/v1.5-7B/v1.5-13B]**](https://github.com/haotian-liu/LLaVA) | [**MiniGPT-4-[v1-7B/v1-13B/v2-7B]**](https://github.com/Vision-CAIR/MiniGPT-4) |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [**mPLUG-Owl2**](https://github.com/X-PLUG/mPLUG-Owl/tree/main/mPLUG-Owl2)🎞️ | [**OpenFlamingo-v2**](https://github.com/mlfoundations/open_flamingo)🎞️ | [**PandaGPT-13B**](https://github.com/yxuansu/PandaGPT)      | [**Qwen-VL**](https://huggingface.co/Qwen/Qwen-VL)🎞️🚅, [**Qwen-VL-Chat**](https://huggingface.co/Qwen/Qwen-VL-Chat)🎞️**🚅** |
| [**VisualGLM-6B**](https://huggingface.co/THUDM/visualglm-6b)🚅 | [**InternLM-XComposer-7B**](https://huggingface.co/internlm/internlm-xcomposer-7b)🚅🎞️ | [**ShareGPT4V-[7B/13B]**](https://sharegpt4v.github.io)🚅     | [**TransCore-M**](https://github.com/PCIResearch/TransCore-M) |
| [**LLaVA (XTuner)**](https://huggingface.co/xtuner/llava-internlm-7b)🚅 | [**CogVLM-17B-Chat**](https://huggingface.co/THUDM/cogvlm-chat-hf)🚅 | [**SharedCaptioner**](https://huggingface.co/spaces/Lin-Chen/Share-Captioner)🚅 | [**CogVLM-Grounding-Generalist**](https://huggingface.co/THUDM/cogvlm-grounding-generalist-hf)🚅 |
| [**Monkey**](https://github.com/Yuliang-Liu/Monkey)🚅         | [**EMU2 / EMU2-Chat**](https://github.com/baaivision/Emu)🚅🎞️  | [**Yi-VL-[6B/34B]**](https://huggingface.co/01-ai/Yi-VL-6B)  | [**MMAlaya**](https://huggingface.co/DataCanvas/MMAlaya)🚅    |
| [**InternLM-XComposer2-7B**](https://huggingface.co/internlm/internlm-xcomposer2-vl-7b)🚅🎞️ | [**MiniCPM-V**](https://huggingface.co/openbmb/MiniCPM-V)🚅   | [**OmniLMM-12B**](https://huggingface.co/openbmb/OmniLMM-12B) | [**InternVL-Chat Series**](https://github.com/OpenGVLab/InternVL)🚅 |
| [**DeepSeek-VL**](https://github.com/deepseek-ai/DeepSeek-VL/tree/main)🎞️ | [**LLaVA-NeXT**](https://llava-vl.github.io/blog/2024-01-30-llava-next/)🚅 |                                                              |                                                              |

🎞️: Support multiple images as inputs, via the `interleave_generate` interface.

🚅: Model can be used without any additional configuration / operation.

**Transformers Version Recommendation: **

Note that some VLMs may not be able to run under certain transformer versions, we recommend the following settings to evaluate each VLM:

- **Please use** `transformers==4.33.0` **for**: `Qwen series`, `Monkey series`, `InternVL series`, `InternLM-XComposer Series`, `mPLUG-Owl2`, `OpenFlamingo v2`, `IDEFICS series`, `VisualGLM`, `MMAlaya`, `SharedCaptioner`, `MiniGPT-4 series`, `InstructBLIP series`,  `PandaGPT`.
- **Please use** `transformers==4.37.0 ` **for**: `LLaVA series`, `ShareGPT4V series`, `TransCore-M`, `LLaVA (XTuner)`, `CogVLM Series`, `EMU2 Series`, `Yi-VL Series`, `MiniCPM-V`, `OmniLMM-12B`, `DeepSeek-VL series`.
- **Please use** `transformers==4.39.0 ` **for**: `LLaVA-Next series`.

```python
# Demo
from vlmeval.config import supported_VLM
model = supported_VLM['idefics_9b_instruct']()
# Forward Single Image
ret = model.generate('assets/apple.jpg', 'What is in this image?')
print(ret)  # The image features a red apple with a leaf on it.
# Forward Multiple Images
ret = model.interleave_generate(['assets/apple.jpg', 'assets/apple.jpg', 'How many apples are there in the provided images? '])
print(ret)  # There are two apples in the provided images.
```

## 🏗️ QuickStart

See [QuickStart](/Quickstart.md) for a quick start guide.

## 🛠️ Development Guide

To develop custom benchmarks, VLMs, or simply contribute other codes to **VLMEvalKit**, please refer to [Development_Guide](/Development.md).

## 🎯 The Goal of VLMEvalKit

**The codebase is designed to:**

1. Provide an **easy-to-use**, **opensource evaluation toolkit** to make it convenient for researchers & developers to evaluate existing LVLMs and make evaluation results **easy to reproduce**.
2. Make it easy for VLM developers to evaluate their own models. To evaluate the VLM on multiple supported benchmarks, one just need to **implement a single `generate` function**, all other workloads (data downloading, data preprocessing, prediction inference, metric calculation) are handled by the codebase.

**The codebase is not designed to:**

1. Reproduce the exact accuracy number reported in the original papers of all **3rd party benchmarks**. The reason can be two-fold:
   1. VLMEvalKit uses **generation-based evaluation** for all VLMs (and optionally with **LLM-based answer extraction**). Meanwhile, some benchmarks may use different approaches (SEEDBench uses PPL-based evaluation, *eg.*). For those benchmarks, we compare both scores in the corresponding result. We encourage developers to support other evaluation paradigms in the codebase.
   2. By default, we use the same prompt template for all VLMs to evaluate on a benchmark. Meanwhile, **some VLMs may have their specific prompt templates** (some may not covered by the codebase at this time). We encourage VLM developers to implement their own prompt template in VLMEvalKit, if that is not covered currently. That will help to improve the reproducibility.

## 🖊️ Citation

If you use VLMEvalKit in your research or wish to refer to the published OpenSource evaluation results, please use the following BibTeX entry and the BibTex entry corresponding to the specific VLM / benchmark you used.

```bib
@misc{2023opencompass,
    title={OpenCompass: A Universal Evaluation Platform for Foundation Models},
    author={OpenCompass Contributors},
    howpublished = {\url{https://github.com/open-compass/opencompass}},
    year={2023}
}
```

## 💻 Other Projects in OpenCompass

- [opencompass](https://github.com/open-compass/opencompass/): An LLM evaluation platform, supporting a wide range of models (LLaMA, LLaMa2, ChatGLM2, ChatGPT, Claude, etc) over 50+ datasets.
- [MMBench](https://github.com/open-compass/MMBench/): Official Repo of "MMBench: Is Your Multi-modal Model an All-around Player?"
- [BotChat](https://github.com/open-compass/BotChat/): Evaluating LLMs' multi-round chatting capability.
- [LawBench](https://github.com/open-compass/LawBench): Benchmarking Legal Knowledge of Large Language Models.
