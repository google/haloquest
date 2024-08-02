# HaloQuest

Welcome to the repository of our ECCV 2024 paper, [**HaloQuest: A Visual Hallucination Dataset for Advancing Multimodal Reasoning**](https://arxiv.org/abs/2407.15680). This repository contains a [colab](https://github.com/google/haloquest/blob/main/HaloQuest_Colab.ipynb) that shows how to load the HaloQuest data and how to use the Auto-Eval system.

Code to reproduce the experiments in the paper is available [here](https://github.com/ZhecanJamesWang/HaloQuest).

[Unofficial Project Page](https://haloquest.github.io/)

![image](./example-image.png)

## Updates
- 2024.07.22: Our paper is on arxiv

## Dataset Description

### Summary

**HaloQuest** is a novel visual question answering (VQA) dataset that focuses on multimodal hallucination in vision-language models (VLMs). It contains **7,748** examples with a combination of real and synthetically generated images, annotated with **questions** and **answers** designed to trigger and evaluate hallucinations.

### Supported Tasks

**HaloQuest** supports tasks related to **hallucination detection and reduction** in VLMs, providing a challenging benchmark for **Visual Question Answering**. The dataset is useful for both evaluation and fine-tuning purposes, aiming to advance multimodal reasoning.

## Dataset Details

### Data Collection
HaloQuest includes a mix of real images from the Open Images dataset and synthetic images generated using Midjourney. Images were curated based on interest and comprehensibility. Questions and answers were crafted by humans and large language models (LLMs), focusing on false premises, visually challenging questions, and questions with insufficient context.

![image](./data-collection-pipeline.png)


### Data Splits
The dataset is split into training and evaluation sets. The following table provides detailed statistics for each subset.

|                | Real Images | Synthetic Images | False Premise Questions | Visually Challenging Questions | Insufficient Context Questions | Total Entries |
|----------------|:-----------:|:----------------:|:-----------------------:|:-----------------------------:|:-----------------------------:|:-------------:|
| Training Set   | 2985        | 4155             | 2698                    | 2973                          | 1469                          | 7140          |
| Evaluation Set | 217         | 391              | 304                     | 183                           | 121                           | 608           |
| Total          | 3202        | 4546             | 3002                    | 3156                          | 1590                          | 7748          |

## Leaderboard

| Model (#Param)     | Rank | Overall | Generated         | Real             | False Premise      | Visually Challenging | Insufficient Context |
|--------------------|------|---------|-------------------|------------------|--------------------|----------------------|----------------------|
|                    |      | Human Eval | Auto-Eval | Human Eval | Auto-Eval | Human Eval | Auto-Eval | Human Eval | Auto-Eval | Human Eval | Auto-Eval | Human Eval | Auto-Eval | Human Eval | Auto-Eval |
| Gemini 1.5 Pro     | 1    | 76.1    | 77.9    | 74.7    | 78.3    | 78.7    | 77.2    | 80.4    | 83.7    | 57.3    | 56.3    | 91      | 92.5    |
| GPT-4o             | 2    | 68.1    | 63.2    | 68.8    | 63.8    | 66.9    | 62.2    | 68.5    | 65.2    | 58.3    | 55.2    | 80.6    | 68.7    |
| GPT-4              | 3    | 62.9    | 61.2    | 64.3    | 61.1    | 60.6    | 61.4    | 64.7    | 63      | 46.9    | 44.8    | 80.6    | 79.1    |
| BEiT-3 (0.7B)      | 4    | 35.9    | 40      | 41.2    | 44.3    | 26.3    | 32.3    | 24.1    | 28.4    | 36.6    | 36.1    | 9.1     | 10.7    |
| InstructBLIP (12B) | 5    | 25.5    | 28.5    | 28.4    | 31.5    | 20.3    | 23      | 28.4    | 32      | 33.3    | 33.9    | 6.6     | 11.6    |
| InstructBLIP (8B)  | 6    | 25      | 27.3    | 28.4    | 29.7    | 18.9    | 23      | 28.4    | 32      | 6.6     | 11.6    | 33.3    | 33.9    |
| BLIP2 (12B)        | 7    | 21.1    | 22.5    | 24.8    | 26.1    | 14.29   | 16.1    | 16.8    | 19.5    | 35.5    | 32.8    | 9.9     | 14.9    |
| MiniGPT4 (13B)     | 8    | 18.7    | 25.2    | 18.2    | 24      | 18.9    | 27.2    | 16.2    | 21.5    | 10.4    | 13.7    | 36.4    | 51.2    |
| MiniGPT4 (7B)      | 9    | 18.6    | 19.1    | 18.1    | 19.4    | 18      | 18.4    | 13.2    | 13.2    | 26.5    | 27.3    | 15.7    | 16.5    |
| Open-flamingo (9B) | 10   | 13.8    | 15      | 16.1    | 17.1    | 9.7     | 11.1    | 13.2    | 13.9    | 19.1    | 21.3    | 7.4     | 8.3     |
| LLaVA (13B)        | 11   | 10.9    | 10.9    | 12.3    | 12.8    | 8.2     | 7.4     | 2.3     | 1.7     | 30.6    | 31.2    | 2.5     | 3.3     |
| BLIP2 (8B)         | 12   | 10.9    | 11.8    | 11.5    | 11.8    | 9.7     | 12      | 5       | 4.6     | 26.8    | 26.8    | 1.7     | 6.6     |
| mPLUG-Owl1 (7B)    | 13   | 9.7     | 8.7     | 11.3    | 10.2    | 6.9     | 6       | 1       | 0.3     | 29      | 26.8    | 2.5     | 2.5     |
| mPLUG-Owl2 (7B)    | 14   | 9.2     | 10.4    | 11      | 11.3    | 6       | 8.8     | 0.8     | 3.3     | 28.4    | 27.9    | 0.8     | 3.3     |
| OFA (1B)           | 15   | 8.7     | 10.2    | 9.7     | 11.3    | 6.9     | 8.3     | 5       | 6.3     | 19.7    | 20.2    | 1.7     | 5       |
| Open-flamingo (3B) | 16   | 6.9     | 8.2     | 7.4     | 8.7     | 6       | 7.4     | 0.7     | 1.3     | 19.1    | 21.3    | 4.1     | 5.8     |


## Contributions

[Zhecan Wang](https://www.zhecanwang.com/)\*, [Garrett Bingham](https://garrettbingham.com/)\*, [Adams Wei Yu](https://adamsyu.github.io/), [Quoc V. Le](https://research.google/people/quoc-v-le/?&type=google), [Thang Luong](https://nlp.stanford.edu/~lmthang/), [Golnaz Ghiasi](https://research.google/people/golnaz-ghiasi/?&type=google)

(\* ZW and GB are main contributors. ZW did some work while at Google DeepMind.)

## Citing this work

```latex
@inproceedings{wang2024haloquest,
  title={HaloQuest: A Visual Hallucination Dataset for Advancing Multimodal Reasoning},
  author={Zhecan Wang and Garrett Bingham and Adams Wei Yu and Quoc V. Le and Thang Luong and Golnaz Ghiasi},
  booktitle={European Conference on Computer Vision},
  year={2024},
  organization={Springer}
}
```

## License and disclaimer

Copyright 2024 DeepMind Technologies Limited

All software is licensed under the Apache License, Version 2.0 (Apache 2.0);
you may not use this file except in compliance with the Apache 2.0 license.
You may obtain a copy of the Apache 2.0 license at:
https://www.apache.org/licenses/LICENSE-2.0

All other materials are licensed under the Creative Commons Attribution 4.0
International License (CC-BY). You may obtain a copy of the CC-BY license at:
https://creativecommons.org/licenses/by/4.0/legalcode

Image URLs are from the [Open Images Dataset v7](https://storage.googleapis.com/openimages/web/factsfigures_v7.html#publications)
and [Midjourney Showcase](https://www.midjourney.com/showcase). Images may be
individually licensed and you should verify the license for each image yourself.

Unless required by applicable law or agreed to in writing, all software and
materials distributed here under the Apache 2.0 or CC-BY licenses are 
distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied. See the licenses for the specific language governing
permissions and limitations under those licenses.

This is not an official Google product.
