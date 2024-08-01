# HaloQuest

Welcome to the repository of our ECCV 2024 paper, [**HaloQuest: A Visual Hallucination Dataset for Advancing Multimodal Reasoning**](https://arxiv.org/abs/2407.15680). This repository contains a [colab](https://github.com/google/haloquest/blob/main/HaloQuest_Colab.ipynb) that shows how to load the HaloQuest data and how to use the Auto-Eval system.

Code to reproduce the experiments in the paper is available [here](https://github.com/ZhecanJamesWang/HaloQuest).


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
