<div align="center">
<h1>Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?</h1>


[Yang Yue](https://yueyang130.github.io/)<sup>1*</sup>†,  [Zhiqi Chen](https://zhiqichen05.github.io/)<sup>1*</sup>,  [Rui Lu](https://lr32768.github.io/)<sup>1</sup>,  [Andrew Zhao](https://andrewzh112.github.io/)<sup>1</sup>,  [Zhaokai Wang](https://www.wzk.plus/)<sup>2</sup>,  [Shiji Song](https://scholar.google.com/citations?user=rw6vWdcAAAAJ&hl=zh-TW)<sup>1</sup>,  [Gao Huang](http://www.gaohuang.net/)<sup>1‡</sup>  

<sup>1</sup> Tsinghua University, LeapLab  <sup>2</sup> Shanghai Jiao Tong University  

<sup>*</sup> Equal Contribution <sup>†</sup> Project Lead <sup>‡</sup> Corresponding Author  


<a href="https://arxiv.org/abs/2504.13837"><img src='https://img.shields.io/badge/arXiv-limit_of_RLVR-red' alt='Paper PDF'>  </a><a href='https://limit-of-rlvr.github.io/'><img src='https://img.shields.io/badge/Project_Page-limit_of_RLVR-green' alt='Project Page'></a> 
 <!-- <a href='https://huggingface.co/datasets/magicr/phyworld'><img src='https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-phyworld-blue'></a> -->
</div>


## Overview

Here's the converted section in Markdown for your `README.md`, preserving the structure and clarity of the original web layout:

---

## 🧠 Introducing Our Work

Recent breakthroughs in reasoning-focused large language models (LLMs)—like OpenAI-o1, DeepSeek-R1, and Kimi-1.5—have heavily relied on **Reinforcement Learning with Verifiable Rewards (RLVR)**. RLVR replaces human annotations with automated rewards (such as verified math answers or passed code tests) to enable scalable self-improvement. While RLVR enhances behaviors like **self-reflection** and **iterative refinement**, a critical question remains in the pursuit of continually self-evolving reasoning abilities:

> **Does RLVR actually expand LLMs' reasoning capabilities, or does it merely optimize existing ones?**

To answer this, we evaluate models using the **pass@k** metric—where success requires only one correct solution among *k* attempts.


![Video Overview](./static/introvideo.gif)  


> *Video: pass@k curves of base models and their zero-RL-trained counterparts across multiple mathematical benchmarks. When k is small, RL-trained models outperform their base versions. However, as k increases to the tens or hundreds, base models consistently catch up with RL-trained models across all benchmarks and LLM families without exception. Eventually, base models surpass RL-trained models.*

Our conclusion:

1. **RL-trained models perform worse than base models in pass@k at large *k*.**  
   RL-trained models beat base models at low sampling sizes, but base models **consistently outperform them** at larger *k*. Manual inspection shows that base models generate **diverse reasoning paths**, often producing at least one correct solution, even for tasks thought to require RL training.

2. **RL boosts sampling efficiency but reduces the reasoning capacity boundary.**  
   RLVR-trained models only generate reasoning paths **already present in the base model**. This training biases the model toward previously rewarded solutions, sacrificing exploration. RLVR doesn't expand the model’s problem-solving potential—it just sharpens what’s already there.

3. **RLVR algorithms perform similarly and remain far from optimal.**  
   Comparing PPO, GRPO, and Reinforce++, we find only **minor differences**. The gap in sampling efficiency (∆SE) stays large, suggesting that all current RL approaches fall **well short of optimal performance**.

4. **RLVR and distillation are fundamentally different.**  
   While RLVR improves sampling, **distillation can introduce new knowledge**. Distilled models often expand their reasoning ability, unlike RLVR-trained models, which remain **bounded by the base model's capacity**.


## Citation

If you use this work, please cite:

```bibtex
@article{yue2025limit-of-rlvr,
  title={Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?},
  author={Yue, Yang and Chen, Zhiqi and Lu, Rui and Zhao, Andrew and Wang, Zhaokai and Yue, Yang and Song, Shjiji and Huang, Gao},
  journal={arXiv preprint arXiv:2504.13837},
  year={2025}
}
```




