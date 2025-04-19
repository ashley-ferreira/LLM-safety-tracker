# LLM Safety Tracking
Technical Appendix for **Are Large Language Models Actually Getting Safer?**

## Overview
This repository serves as the technical appendix for a forthcoming working paper to be published by the [Centre for International Governance Innovation (CIGI) Digital Policy Hub](https://www.cigionline.org/digital-policy-hub/working-papers/).

This project aims to analyze the safety performance of LLMs from frontier AI labs over time, with a focus on models from OpenAI, Anthropic, and Meta. 


## Data Sources
The analysis uses data from **[Libra-Leaderboard](https://leaderboard.librai.tech/LeaderBoard)**, **[Salad-Bench](https://adwardlee.github.io/salad_bench/leaderboard.html)**,  **[DecodingTrust](https://huggingface.co/spaces/AI-Secure/llm-trustworthy-leaderboard)**, **[SafetyBench](https://llmbench.ai/safety)**, and the **[HELM Safety Leaderboard](https://crfm.stanford.edu/helm/safety/v1.5.0/)** (which is comprised of scores on [HarmBench](https://www.harmbench.org/explore), [SimpleSafetyTests](https://milanlproc.github.io/publication/2023-simplesafetytests/), [BBQ](https://huggingface.co/datasets/heegyu/bbq), [Anthropic Red Team](https://www.anthropic.com/research/red-teaming-language-models-to-reduce-harms-methods-scaling-behaviors-and-lessons-learned), as well as [XSTest](https://huggingface.co/datasets/walledai/XSTest)).


Performance on these leaderboards and benchmark results are extracted for OpenAI, Anthropic, and Meta models. Often benchmarks provide a more granular breakdown of performance across specific categories or methods of evaluation. The table below outlines which specific values were used for this analysis. 

| Benchmark/Leaderboard | Metric Used | Scale |
|-----------|-------------|-------|
| Libra-Leaderboard | Safety Score | 0-100 |
| Salad-Bench | Average | 0-100 |
| DecodingTrust | Average | 0-100 |
| SafetyBench | English Average | 0-100 |
| HELM Safety Leaderboard | All values from v1.5.0 | 0-1 |


## Usage
The Jupyter notebook `results_plotting.ipynb` contains the code used to generate the visualizations from the raw data files.


## Limitations 
This is currently a working paper by an early-career researcher, and any feedback on this work would be greatly appreciated. Some important limitations to consider: until a more thorough peer review is conducted, there are likely some uncaught errors; this study only uses a small selection of models on only a few evaluations so it is not all-encompassing; release and snapshot dates are only a rough proxy for the model development cycles and the models themselves are often quite different and hard to compare; and finally, benchmarks themselves are ever-evolving and are a flawed way of measuring safety as a whole (safety seems extremely hard to quantify). 


## Citations
If you use this specific analysis in your research, please cite:

```bibtex
@misc{ferreira2024llmsafetytracker,
    author = {Ferreira, Ashley},
    title = {Are Large Language Models Actually Getting Safer?},
    year = {2024},
    publisher = {Centre for International Governance Innovation},
    url = {https://www.cigionline.org/digital-policy-hub/working-papers/}
}
```
If you would like to use the data from the underlying benchmarks, please cite them specifically, I've included an non-exhaustive list of citations below:

```bibtex
@misc{li2024libraleaderboardresponsibleaibalanced,
    title={Libra-Leaderboard: Towards Responsible AI through a Balanced Leaderboard of Safety and Capability},
    author={Haonan Li and Xudong Han and Zenan Zhai and Honglin Mu and Hao Wang and Zhenxuan Zhang and Yilin Geng and Shom Lin and Renxi Wang and Artem Shelmanov and Xiangyu Qi and Yuxia Wang and Donghai Hong and Youliang Yuan and Meng Chen and Haoqin Tu and Fajri Koto and Tatsuki Kuribayashi and Cong Zeng and Rishabh Bhardwaj and Bingchen Zhao and Yawen Duan and Yi Liu and Emad A. Alghamdi and Yaodong Yang and Yinpeng Dong and Soujanya Poria and Pengfei Liu and Zhengzhong Liu and Xuguang Ren and Eduard Hovy and Iryna Gurevych and Preslav Nakov and Monojit Choudhury and Timothy Baldwin},
    year={2024},
    eprint={2412.18551},
    archivePrefix={arXiv},
    primaryClass={cs.CL},
    url={https://arxiv.org/abs/2412.18551},
}

@article{li2024salad,
    title={Salad-bench: A hierarchical and comprehensive safety benchmark for large language models},
    author={Li, Lijun and Dong, Bowen and Wang, Ruohui and Hu, Xuhao and Zuo, Wangmeng and Lin, Dahua and Qiao, Yu and Shao, Jing},
    journal={arXiv preprint arXiv:2402.05044},
    year={2024}
}

@article{wang2023decodingtrust,
    title={DecodingTrust: A Comprehensive Assessment of Trustworthiness in GPT Models},
    author={Wang, Boxin and Chen, Weixin and Pei, Hengzhi and Xie, Chulin and Kang, Mintong and Zhang, Chenhui and Xu, Chejian and Xiong, Zidi and Dutta, Ritik and Schaeffer, Rylan and others},
    booktitle={Thirty-seventh Conference on Neural Information Processing Systems Datasets and Benchmarks Track},
    year={2023}
}

@misc{zhang2024safety,
    title={SafetyBench: Evaluating the Safety of Large Language Models}, 
    author={Zhexin Zhang and Leqi Lei and Lindong Wu and Rui Sun and Yongkang Huang and Chong Long and Xiao Liu and Xuanyu Lei and Jie Tang and Minlie Huang},
    year={2024},
    eprint={2309.07045},
    archivePrefix={arXiv},
    primaryClass={cs.CL},
    url={https://arxiv.org/abs/2309.07045}, 
}

@article{wang2023libra,
    title={Libra: A Holistic AI Safety Benchmark for Evaluating the Trustworthiness of Large Language Models},
    author={Wang, Junjie and Yang, Bei and Bai, Jingwei and Song, Runji and Yue, Wenwei and Wang, Shuo and Lang, James and Zhang, Wei and Zhang, Ji and others},
    journal={arXiv preprint arXiv:2309.08558},
    year={2023}
}

@article{liang2023holistic,
    title={Holistic Evaluation of Language Models},
    author={Percy Liang and Rishi Bommasani and Tony Lee and Dimitris Tsipras and Dilara Soylu and Michihiro Yasunaga and Yian Zhang and Deepak Narayanan and Yuhuai Wu and Ananya Kumar and Benjamin Newman and Binhang Yuan and Bobby Yan and Ce Zhang and Christian Alexander Cosgrove and Christopher D Manning and Christopher Re and Diana Acosta-Navas and Drew Arad Hudson and Eric Zelikman and Esin Durmus and Faisal Ladhak and Frieda Rong and Hongyu Ren and Huaxiu Yao and Jue WANG and Keshav Santhanam and Laurel Orr and Lucia Zheng and Mert Yuksekgonul and Mirac Suzgun and Nathan Kim and Neel Guha and Niladri S. Chatterji and Omar Khattab and Peter Henderson and Qian Huang and Ryan Andrew Chi and Sang Michael Xie and Shibani Santurkar and Surya Ganguli and Tatsunori Hashimoto and Thomas Icard and Tianyi Zhang and Vishrav Chaudhary and William Wang and Xuechen Li and Yifan Mai and Yuhui Zhang and Yuta Koreeda},
    journal={Transactions on Machine Learning Research},
    issn={2835-8856},
    year={2023},
    url={https://openreview.net/forum?id=iO4LZibEqW},
    note={Featured Certification, Expert Certification}
}
```
