---
title: "EndoComparer: Comparative Surgical Video Question Answering with Pseudo-Siamese Visual Adaptation and Perceive-then-Compare Reasoning"
collection: publications
category: preprint
permalink: /publication/2026-11-14-endocomparer
date: 2026-11-14
authors: 'Shi Li, Lalith Sharan, Joël L. Lavanchy, Kun Yuan, Lorenzo Arboit, Nabani Banik, Elif Yazici, Maria Vannucci, Vinkle Srivastav, Pietro Mascagni, Nicolas Padoy'
venue: 'arXiv preprint'
image: 'images/endocomparer.png'
paperurl: ''
arxiv: 'https://arxiv.org/abs/2611.19578'
project: 'https://camma-public.github.io/endocomparer/'
code: 'https://github.com/CAMMA-public/endocomparer'
demo: ''
media: ''
---
Purpose: Surgical training benefits from explicit comparison between cases: in patient condition, in technique and in skill proficiency. Surgical vision-language models (VLMs) offer a promising and flexible interface for this purpose. Yet current VLMs typically see one video at a time, and they often fall short when asked to compare videos. Methods: We propose EndoComparer, a VLM for comparative surgical video question answering with two components. (a) A Pseudo-Siamese Visual LoRA (PSVL) gives each video slot its own low-rank adapter over a shared frozen vision encoder, separating the two videos in the visual pathway at the cost of a single encoder pass. (b) A Perceive-then-Compare chain of thought (PtC-CoT) trains the model to first state what each video shows, then derive the answer from these statements. We further curate EndoDiffVQA, a benchmark of nearly 11K multiple-choice questions on video-pair over cholecystectomy and gastric bypass procedures, covering anatomy, tool, action and skill. Results: EndoComparer outperforms strong generalist and surgical VLMs on detecting and specifying difference between videos. Ablations show that two proposed components contribute complimentarily, and the model remains more robust under a video-swap control that exposes confusion between the two videos. Conclusion: Providing a dedicated visual reasoning path through PSVL and PtC-CoT makes cross-case comparison of surgical videos more robust for VLMs. EndoDiffVQA and EndoComparer provide a benchmark and a strong baseline for this task.
