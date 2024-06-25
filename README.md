# EDA_LLM

## Guide

本推文整理了 2023 年和 2024 年关于 LLM4EDA 方面论文，尽可能覆盖最近和以往的工作。如有疏漏或者问题，请及时联系我。

---

## List

### 2023

---

1. **ChipNeMo: Domain-Adapted LLMs for Chip Design** [paper](https://arxiv.org/abs/2311.00176) [talk](https://www.bilibili.com/video/BV1Jz421R7Fj/)

_Liu, Mingjie and Ene, Teodor-Dumitru and Kirby, Robert and Cheng, Chris and Pinckney, Nathaniel and Liang, Rongjian and Alben, Jonah and Anand, Himyanshu and Banerjee, Sanmitra and Bayraktaroglu, Ismet and others_

arXiv 2023

摘要：该论文提出了 ChipNeMo，旨在探索 LLM 在工业芯片中应用。该论文采用以下领域自适应技术：领域自适应分词（domain-adaptive tokenization）、领域自适应持续预训练（domain-adaptive continued pretraining）、模型对齐（model alignment with domain-specific instructions）、领域自适应检索模型（domain-adapted retrieval models）。该论文在三种芯片 LLM 应用上评估了这些方法：工程助理聊天机器人（engineering assistant chatbot）、EDA 脚本生成（EDA script generation）和错误摘要和分析（bug summarization and analysis）。该论文实验评估表明，领域自适应的语言模型预训练可以在领域相关下游任务上取得优于基础 LLaMA2 模型性能，而不会降低通用能力。特别是最大的模型 ChipNeMo-70B 在工程助理聊天机器人和 EDA 脚本生成两个应用案例中表现优于 GPT-4，同时在错误摘要和分析也表现出竞争力。这些结果表明领域定制 LLM 在专业应用中有效性方面的潜力。

---

2. **Benchmarking Large Language Models for Automated Verilog RTL Code Generation** [paper](https://ieeexplore.ieee.org/document/10137086) [code](https://github.com/shailja-thakur/VGen)

_Shailja Thakur, Baleegh Ahmad, Zhenxing Fan, Hammond Pearce, Benjamin Tan, Ramesh Karri, Brendan Dolan-Gavitt and Siddharth Garg_

DATE 2023

摘要：Verilog 是一种流行的硬件描述语言，用于数字电路系统建模和设计，生成 Verilog 代码是关键的第一步。该论文探讨了 LLM 生成 Verliog 代码能力，通过在 Github 和 Verilog 教科书上收集的数据集上微调预训练的 LLM。该论文构建了一个包含功能分析（test-benches for functional analysis）和语法测试流程（flow to test the syntax of Verilog code generated）的评估框架。结果表明，经过微调的 LLM 能够生成语法正确的 Verilog 代码（整体准确率为 25.9%）。此外在分析功能正确性（analyze functional correctness）上，经过微调的开源 CodeGen LLM 可以超过 SOTA 模型商用 Codex LLM（总体超过 6.5%）。该论文还提供了训练和评估脚本以及 LLM checkpoints 的开源贡献。

---

3. **A Deep Learning Framework for Verilog Autocompletion Towards Design and Verification Automation** [paper](https://arxiv.org/abs/2304.13840) [code](https://github.com/99EnriqueD/verilog_autocompletion)

_Enrique Dehaerne, Bappaditya Dey, Sandip Halder and Stefan De Gendt_

arXiv 2023

摘要：该论文提出了一个新颖的深度学习框架，用于训练 Verilog 自动补全模型；其次提出了一个从开源仓库获取的文件和代码片段组成的 Verilog 数据集。该框架涉及并且整合在通用编程语言数据上预训练模型，并与目标下游任务相似的数据集上进行微调。通过多种评估指标比较不同的预训练模型（不同 Verilog 数据子集训练）。实验表明，所提框架在 BLEU、ROUGE-L 和 chrF 得分上分别比从头开始训练的模型提高了 9.5%、6.7% 和 6.9%。代码和数据均与开源至 Github。

---

4. **VerilogEval: Evaluating Large Language Models for Verilog Code Generation** [paper](https://ieeexplore.ieee.org/abstract/document/10323812) [code](https://github.com/NVlabs/verilog-eval)

_Mingjie Liu, Nathaniel Pinckney, Brucek Khailany, and Haoxing Ren_

ICCAD 2023

摘要：该论文提出了一种专门评估 LLM 在硬件设计和验证的 Verilog 代码生成环境的基准测试框架。该论文提供了一个全面评估的数据集，包括来自 Verilog 教学网站 HDLBits 的 156 个问题。该评估集包含多种 Verilog 代码生成任务，从简单的组合电路到复杂的有限状态机。通过将生成的设计的暂态模拟输出与黄金解决方案进行比较，自动测试 Verilog 代码完成功能正确性。该论文还展示了提供 LLM 生成的问题-代码对（problem-code pairs）进行监督微调，提高预训练模型 Verilog 代码生成能力。

---

5. **Rtlcoder: Outperforming gpt-3.5 in design rtl generation with our open-source dataset and lightweight solution** [paper](https://arxiv.org/abs/2312.08617) [code](https://github.com/hkust-zhiyao/RTL-Coder)

_Shang Liu, Wenji Fang, Yao Lu , Qijun Zhang, Hongce Zhang and Zhiyao Xie_

arXiv 2023

摘要：使用自然语言指令（natural language instructions）和 LLM 自然生成 RT 了代码最近引起了极大研究兴趣。然而大多数现有方法严重依赖商用 LLM（e.g. ChatGPT），缺乏高质量开源解决方案。该论文提出了一种新的定制化 LLM 方案，用于自动生成 RTL 代码（e.g. Verilog）。这种方法参数量仅 7B，但在所有代表性基准测试中性能均优于 GPT3.5，并且 VerilogEval 基准测试中超过了 GPT4.5。该论文成果得益于新的 RTL 数据集和定制化 LLM 算法，并且完全开源。此外该论文成果将该论文 LLM 量化为 4bit，总大小为 4G，可以在一台笔记本电脑上运行，性能只有轻微下降。这种效率使得 RTL generator 能充当工程师的本地助手，确保所有设计隐私问题得到解决。

---

6. **RTLLM: An Open-Source Benchmark for Design RTL Generation with Large Language Model** [paper](https://ieeexplore.ieee.org/abstract/document/10473904) [code](https://github.com/hkust-zhiyao/RTLLM)

_Yao Lu, Shang Liu, Qijun Zhang, and Zhiyao Xie_

ASP-DAC 2023

摘要：受到 ChatGPT 启发，开始探索 LLM 进行灵活设计，例如基于自然语言指令生成 RTL。然而在现有研究中目标都是相对简单和小规模的，在不同解决方案之间公平对比具有挑战性。此外许多先前工作仅关注设计的正确性，而没有评估生成 RTL 质量。在该论文中提出一个 RTLLM 开源基准用于根据自然语言指令生成设计 RTL。为了系统评估自动生设计 RTL，该论文总结了 3 个渐进目标：语法目标（syntax goal）、功能目标（functionality goal）、设计质量目标（design quality goal）。该基准可以自动提供对任何基于 LLM 的解决方案定量评估。此外该论文提出一种简单易用且效果显著的提示工程（prompt engineering）——自我规划（self-planning），在该论文提出的框架中显著提高了 GPT-3.5 的性能。

---

7. **Llm4eda: Emerging progress in large language models for electronic design automation** [paper](https://arxiv.org/abs/2401.12224) [code](https://github.com/Thinklab-SJTU/Awesome-LLM4EDA)

_Ruizhe Zhong, Xingbo Du, Shixiong Kai, Zhentao Tang, Siyuan Xu, Hui-Ling Zhen, Jianye Hao, Qiang Xu, Mingxuan Yuan and Junchi Yan_

arXiv 2023

摘要：现代芯片设计复杂性和规模正在迅速增大，EDA 广泛用于解决整个芯片过程中遇到的挑战。然而超大规模集成电路（VLSI）发展使得芯片设计耗时又耗费资源，此外中间人类控制为寻求最佳解决方案至关重要。系统设计初期，电路通常用 HDL（Hardware Description Language）表示。LLM 已经展现在上下文理解（context understanding）、逻辑生成（logic reasoning）、回答生成（answer generation）的能力。电路可以用 HDL 表示，可以合理质疑 LLM 是否可以在 EDA 领域应用，以完全实现自动化的芯片设计，生成有更高 PPA（power, performance, and area）的电路。该论文对 LLM 在 EDA 领域应用做了系统研究，将分类为以下几种情况：辅助聊天机器人（assistant chatbot）、HDL 和脚本生成（HDL and script generation）、HDL 验证和分析（HDL verification and analysis）。此外该论文强调未来研究方向，重点是将 LLM 应用于逻辑综合（logic synthesis）、物理设计（physical design）、多模态特征提取（multimodal feature extraction）和电路对齐（alignment of circuits）。该论文开源至 Github。

---

8. **Chip-chat: Challenges and opportunities in conversational hardware design** [Workshop](https://ieeexplore.ieee.org/abstract/document/10299874)

_Jason Blocklove, Siddharth Garg, Ramesh Karri, Hammond Pearce_

MLCAD 2023

摘要：商业上可用的指令调优 LLM（e.g. ChatGPT, Bard）声称能够用于各种编程语言生成，但是针对硬件研究仍然缺乏。该论文探索了在硬件设计中 LLM 最新进展和面临的挑战和机遇。该论文进行了一项案例研究，硬件工程师和 LLM 沟通设计了一个基于 8 为累加器的微处理器体系架构，然后 Skyeater 130nm 上完成处理器流片，该论文认为这是世界上第一个由 AI 编写的 HDL 用于流片的实例。

---

9. **ChipGPT: How far are we from natural language hardware design** [paper](https://arxiv.org/abs/2305.14019)

_Kaiyan Chang, Ying Wang, Haimeng Ren, Mengdi Wang, Shengwen Liang, Yinhe Han, Huawei Li, and Xiaowei Li_

arXiv 2023

摘要：该论文试图演示出一个自动化设计环境，该环境利用 LLM 从自然语言生成硬件逻辑设计。为了实现更易访问和更高效的芯片开发流程，该论文提出了一个基于 LLM 的可扩展性四阶段零代码逻辑设计框架（scalable four-stage zero-code logic design framework），无需重新训练或者微调。首先 ChipGPT 通过为 LLM 生成提示，然后 LLM 生成初始 Verilog 程序。其次一个输出管理器会将这些程序收集到最终设计空间之前进行叫纠正和优化。最终 ChipGPT 将这些空间中搜索以选择符合目标指标的最佳设计。评估结果对 LLM 能否为某些规范生成正确和完整的硬件描述语言能力。结果表明 ChipGPT 提高了可编程性和可控性，与以往的工作和原生 LLM 相比，显示了更广泛的设计优化空间。

---

10. **VeriGen: A Large Language Model for Verilog Code Generation** [paper](https://dl.acm.org/doi/abs/10.1145/3643681) [code](https://github.com/shailja-thakur/VGen)

_Shailja Thakur, Baleegh Ahmad, Hammond Pearce, Benjamin Tan, Brendan Dolan-Gavitt, Ramesh Karri, and Siddharth GargAuthors Info and Claims_

DATE 2023

摘要：该论文探索了 LLM 通过生成高质量 Verilog 代码来自动化硬件设计能力。该论文从 Github 和 Verilog 教材中数据集对 LLM 进行了微调。该论文专门设计测试套件，包含自定义问题集和测试台，用于评估生成 Verilog 代码功能正确性。该论文微调的开源 CodeGen-16B 模型整体上优于商业 SOTA 模型 GPT-3.5-turbo，提示 1.1%。在使用更多样化和复杂问题集进行测试时，该论文发现微调模型在某些场景表现出与最先进的 GPT-3.5-turbo 相媲美的性能，某些条件下表现优异。注意的是在生成语法正确 Verilog 代码方面表现 41% 改进。该论文将训练/评估和 LLM checkpoint 开源至 Github。

---

11. **Gpt4aigchip: Towards next-generation ai accelerator design automation via large language models** [paper](https://ieeexplore.ieee.org/abstract/document/10323953)

_Yonggan Fu, Yongan Zhang, Zhongzhi Yu, Sixu Li, Zhifan Ye, Chaojian Li, Cheng Wan and Yingyan (Celine) Lin_

ICCAD 2023

摘要：AI 的显著能力和复杂特性极大地提升了对专用 AI 加速器的需求。然而为各种 AI 工作负载设计这些加速器仍然既费时又费力。该论文为研究利用 LLM 自动化 AI 加速器设计可能性，开发了 GPT4AIGChip，一个旨在通过使用人类自然语言代替领域特定语言来简化和普及 AI 加速器设计的框架。利用上下文学习（in-context learning）的自动演示增强生成（automated demo-augmented prompt-generation）pipeline，用于 LLM 驱动的自动化 AI 加速器生成。该论文提及这是第一个用于 LLM 驱动的自动化 AI 加速器生成 pipeline。因此该论文期望框架和简介能成为下一代 LLM 驱动设计自动化工具创新的催化剂。

---

### 2024

---

1. **AnalogCoder: Analog Circuit Design via Training-Free Code Generation** [paper](https://arxiv.org/abs/2405.14918) [code](https://github.com/laiyao1/AnalogCoder)

_Yao Lai,  Sungyoung Lee,  Guojin Chen, Souradip Poddar, Mengkang Hu, David Z. Pan and Ping Luo_

arXiv 2024

摘要：模拟电路设计是现代芯片技术中一项重要任务，主要集中在选择元件类型、连接性和参数选择上，确保电路正常功能。尽管 LLM 在数字电路设计方面取得进展，但模拟电路的复杂性和数据稀缺性带来了显著挑战。该论文为解决这些问题引入 AnalogCoder 一种通过生成 Python 代码生成进行模拟电路设计的 training-free LLM agent。首先 AnalogCoder 将反馈增强的设计流程（feedback-enhanced design flow）和特定领域的提示工程（doman-specific prompt engineering）结合在一起，使得模拟电路的自动化和自我纠正设计成功率较高。其次提出了一个电路设计语料库（circuit tool library），用于存档成功设计的模块子电路，简化复合电路创建。第三针对广泛覆盖模拟电路任务基准进行广泛实验，表明 AoalogCoder 优于其他 LLM 方法，成功设计 20 个电路，比标准 GPT-4o 多出 5 个。该研究相信 AnalogCoder 可以显著改善劳动密集型电路设计过程，使得非专业人士也可以设计电路。代码和基准在 Github 上开源。

---

2. **AutoChip: Automating HDL Generation Using LLM Feedback** [paper](https://arxiv.org/abs/2311.04887) [code](https://github.com/shailja-thakur/AutoChip)

_Shailja Thakur, Jason Blocklove, Hammond Pearce, Benjamin Tan, Siddharth Garg and Ramesh Karri_

DAC 2024

摘要：该论文提出了 AutoChip，这是第一种采用反馈驱动（feedback-driven）的全自动方法，使用最先进的 LLM 来生成 HDL。AutoChip 结合了对话型 LLM 和 Verilog 编译器和仿真输出，以迭代方式生成 Verilog 模块。AutoChip 首先使用提示来生成初始模块，然后利用编译错误和仿真消息的上下文来改进这个初始模块。该论文使用 HDLBits 的设计提示和测试平台来评估 AutoChip。结果对多个 LLM、这些 LLM 顺序组合以及不同迭代反馈量。在最新的 Verilog 编译器和模拟器上下文提高了现有方法的有效性，产生 Verilog 通过 89.19% 的测用例，比零初始设置高出 24.2%。该论文已将评估脚本和数据集开源在 Github。

---

3. **Rtlfixer: Automatically fixing rtl syntax errors with large language models** [paper](https://arxiv.org/abs/2311.16543) [code](https://github.com/NVlabs/RTLFixer)

_Yun-Da Tsai, Mingjie Liu and Haoxing Ren_

DAC 2024

摘要：该论文提出了一种新的框架——RTLFixer，利用 LLM 自动修正 Verilog 代码中语法错误。尽管 LLM 具有很好的性能，但该论文分析表明，LLM 生成 Verilog 代码中大概 55% 的错误是跟语法相关的，导致编译失败。为了解决这个问题，该论文引入一种新颖的调试框架，该框架采用检索增强生成（RAG）和 ReAct 提示，使 LLMs 能够作为自动代理，在交互式调试代码中提供反馈。这个框架在解决语法错误方面表现出熟练程度，纠正该论文调试数据集中约 98.5% 的编译错误，该错误包括来源 VerilogEval 基准测试的 212 个错误实现。该论文方法在 VerilogEval-Machine 和 VerilogEval-Human 基准测试中分别提高了 32.3% 和 10.1% 的 pass@1 成功率。源码和基准测试在 Github 上开源。

---

4. **LLM-Enhanced Bayesian Optimization for Efficient Analog Layout Constraint Generation** [paper](https://arxiv.org/abs/2406.05250) [code](https://github.com/dekura/LLANA)

_Guojin Chen, Keren Zhu, Seunggeun Kim, Hanqing Zhu, Yao Lai, Bei Yu and David Z. Pan_

arXiv 2024

摘要：模拟版图（layout）规划面临巨大挑战，过程依赖人工，以及大量时间需求和不稳定性。尽管基于贝叶斯优化（BO）的模拟版图综合技术有自动化潜力，但仍存在收敛速度慢和数据需求广泛问题，限制实际应用，该研究提出 LLANA 框架，利用 LLM 增强 BO，通过 LLM 的少量学习能力来更高效生成模拟设计相关的参数约束。实验结果表明 LLANA 不仅获得与 SOTA BO 方法媲美的性能，还优于 LLM 卓越上下文理解和学习效率比，使得模拟电路设计空间探索变得更为高效。代码开源至 Github。

---

5. **BetterV: Controlled Verilog Generation with Discriminative Guidance** [paper](https://openreview.net/forum?id=jKnW7r7de1)

_Zehua PEI, Huiling Zhen, Mingxuan Yuan, Yu Huang, and Bei Yu_

ICML 2024

摘要：IC 产业复杂性日益增加，自动化电路设计方法需求也随之增加。该研究提出一种 Verilog 框架——BetterV，该框架通过对特定领域数据集（domain-specific datasets）处理进行 LLM 微调，并结合生成性判别器（generative discriminators）来引导特定设计需求。从互联网上收集过滤和处理 Verilog 模块，形成一个干净且丰富数据集。指令调优（Instruct-tuning）方法用于微调 LLM，理解 Verilog 知识。此外通过数据增强扩充数据集，用于训练特定下游任务，为 LLM 优化 Verilog 实现提供指导。BetterV 能够生成语法和功能正确的 Verilog，在 VerilogEval 基准表现上优于 GPT-4。在特定任务生成性鉴别器帮助下，BetterV 在各种 EDA 下游任务中取得改进，包括用于综合网表节点减少和 SAT（Boolean Satisfiability）求解验证运行时间减少。

---

6. **LLMs and the Future of Chip Design: Unveiling Security Risks and Building Trust** [paper](https://arxiv.org/abs/2405.07061) [code](https://github.com/DfX-NYUAD/LLM4IC)

_Zeng Wang, Lilas Alrahis, Likhitha Mankali, Johann Knechtel, and Ozgur Sinanoglu_

arXiv 2024

摘要：芯片设计将通过大语言模型、多模态和电路模型（统称为 LxMs）而发生巨大改革。在探索这一充满巨大潜力的新领域同时，社区也必须考虑相关的安全风险以及芯片设计建立信任的必要性。该论文首先回顾了芯片设计中使用 LxMs 的近期热潮。涵盖了硬件描述语言代码生成自动化和电子设计自动化工具 SOTA 模型，e.g. 设计空间探索（design-space exploration）、调优（tuning）、设计人员培训（designer training）。其次该论文从攻击（attack）和防御（defense）两个角度初步回答 LxM 驱动芯片设计的安全性和可靠性问题初步答案。

---

7. **Chateda: A large language model powered autonomous agent for eda** [paper](https://ieeexplore.ieee.org/abstract/document/10485372) [code](https://github.com/wuhy68/ChatEDAv1)

_Haoyuan Wu, Zhuolun He, Xinyun Zhang, Xufeng Yao, Su Zheng, Haisheng Zheng and Bei Yu_

TCAD 2024

摘要：该论文介绍 ChatEDA，一个 LLM AutoMage 驱动的 EDA agent。ChatEDA 通过有效管理任务分解（task decomposition）、脚本生成（script generation）和任务执行（task execution），简化从 RTL 到 GDSII 设计流程。通过全面评估证明 ChatEDA 在处理多样化需求方面的熟练能力，该论文微调的 AutoMage 模型性能也优于 GPT-4 和其他类型的 LLMs。

---

8. **Hdldebugger: Streamlining hdl debugging with large language models** [paper](https://arxiv.org/abs/2403.11671)

_Xufeng Yao, Haoyang Li, Tsz Ho Chan, Wenyi Xiao, Mingxuan Yuan, Yu Huang, Lei Chen and Bei Yu_

KDD 2024

摘要：芯片设计领域，HDL 尤为重要，但由于 HDL 复杂语法和在线资源有限性，难以调试，是一个困难和耗时任务。该论文提出一种由 LLM 辅助的 HDL 调试框架——HDLdebugger，该框架基于逆向工程方法（reverse engineering）生成 HDL 语言调试，检索增强生成（RAG），检索增强 LLM 微调方法。集成这些组件，HDLdebugger 可以自动并简化芯片设计的 HDL 调试。该论文在华为（huawei）提供的 HDL 代码数据集上实验表明，HDLdeugger 性能超过了 13 个 LLM 基线，展示出在 HDL 代码调试方面卓越效果。

---

9. **VerilogReader: LLM-Aided Hardware Test Generation** [paper](https://arxiv.org/abs/2406.04373) [code](https://github.com/magicYang1573/llm-hardware-test-generation)

_Ruiyang Ma, Yuxin Yang, Ziqian Liu, Jiaxi Zhang, Min Li, Junhua Huang and Guojie Luo_

LAD 2024

摘要：测试生成在硬件设计验证中一直是一个关键且耗费人力的过程，该论文研究将 LLM 集成到 CDG（Coverage Directed Test Generation, 覆盖率指导的测试生成）中，其中 LLM 充当 Verilog 阅读器——VerilogReader，准确掌握代码逻辑，从而生成未探索代码分支。该论文使用自行设计 Verilog 基准测试套件，将本文框架与随机测试进行比较。实验表明 VerilogReader 在 LLM 理解范围内设计优于随机测试。该论文还提出提示工程（prompt engineering）优化，增强 LLM 的理解范围和准确性。

---

10. **C2HLSC: Can LLMs Bridge the Software-to-Hardware Design Gap?** [paper](https://arxiv.org/abs/2406.09233)

_Luca Collini, Siddharth Garg and Ramesh Karri_

arXiv 2024

摘要：HLS 工具提供了从 C 代码到硬件设计的快速路径，但兼容性受到代码结构影响。该论文研究 LLM 用于将 C 代码重构未 HLS 兼容格式应用。提供使用 LLM 用于 NIST 800-22 随机性测试（NIST 800-22 randomness tests）、QuickSort 算法（QuickSort algorithm）和 AES-128 HLS 和 C 代码综合（AES-128 into HLS-synthesizable c）。LLM 在用户提示指导下迭代转化 C 代码，实现流数据处理（streaming data）和硬件特定信号（hardware-specific signals）等功能。评估证明 LLM 在帮助硬件设计将常规 C 代码重构为 HSL 可综合 C 代码方面潜力。

---

11. **LaMAGIC: Language-Model-based Topology Generation for Analog Integrated Circuits** [paper](https://openreview.net/forum?id=MjGCD8wk1k)

_Chen-Chia Chang, Yikang Shen, Shaoze Fan, Jing Li, Shun Zhang, Ningyuan Cao, Yiran Chen and Xin Zhang_

ICML 2024

摘要：由于现代应用的复杂性和定制需求，模拟电路的自动化越来越重要。然而现有方法仅开发了需要多次仿真迭代来设计定制电路拓扑的基于搜索的算法，通常这是一个耗时的过程。该研究引入了 LaMAGIC，这是一个基于语言模型的拓扑生成模型（topology generation model），利用监督微调（sft）进行自动化模拟电路设计。LaMAGIC 可以从定制规格中有效生成优化的电路设计。该研究的方法涉及对各种电路输入和输出表达式的详细开发和分析。这些表达式可以确保电路的规范表示，并与 LM 的自回归性质保持一致，有效地解决了将模拟电路表示为图的挑战。实验结果表明，LaMAGIC 在严格的 0.01 公差下达到了高达 96% 的成功率。还检查了 LaMAGIC 的可扩展性和适应性，特别是测试了它在更复杂电路上的性能。该研究不仅展示了语言模型在图生成中的潜力，还为自动化模拟电路设计的未来探索建立了基础框架。

---

12. **VHDL-Eval: A Framework for Evaluating Large Language Models in VHDL Code Generation** [paper](https://arxiv.org/abs/2406.04379) [code](https://vunit.github.io/index.html)

_Prashanth Vijayaraghavan, Luyao Shi, Stefano Ambrogio, Charles Mackin, Apoorva Nitsure, David Beymer and Ehsan Degan_

arXiv 2024

摘要：该论文引入一种评估 LLM 在 VHDL 代码生成任务上框架，并构建一个 VHDL 代码数据集，此数据集通过将 Verilog 评估问题转化成 VHDL 并聚合公开可用 VHDL 问题来构建，总共 202 个问题。为评估生成 VHDL 代码功能正确性，该论文利用一组精心设计的自验证测试（self-verifying testbenches）平台。对不同 LLM 及其变体进行初步评估，包括零样本代码生成（zero-shot code generation）、上下文中学习（ICL）和参数高效微调（PEFT）方法。该研究发现强调现有 LLM 在 VHDL 代码生成方面面临巨大挑战，揭示改进巨大改进空间。该研究还强调了为 VHDL 代码生成模型必要性。

---

13. **ChatPattern: Layout Pattern Customization via Natural Language** [paper](https://arxiv.org/abs/2403.15434)

_Zixiao Wang, Yunheng Shen, Xufeng Yao, Wenqian Zhao, Yang Bai, Farzan Farnia and Bei Yu_

DAC 2024

摘要：现有研究主要关注固定尺寸的布局模式生成，而更实际的自由尺寸模式生成受到的关注较少。该论文提出了一种名为 ChatPattern 的 LLM 驱动框架，用于灵活的模式定制。ChatPattern 采用了一个包括专家 LLM agent 和高度可控布局模式生成器的两部分系统。LLM 代理能够解释自然语言要求并操作设计工具以满足特定需求，而生成器擅长于条件布局生成、模式修改和内存友好的模式扩展。在具有挑战性的模式生成设置上的实验显示了 ChatPattern 合成高质量大规模模式的能力。

---

14. **Large Language Model (LLM) for Standard Cell Layout Design Optimization** [paper](https://arxiv.org/abs/2406.06549)

_Chia-Tung Ho and Haoxing Ren_

arXiv 2024

摘要：标准单元是现在数字电路设计基本组成部分。随着工艺技术向着 2 纳米技术发展，由于布线轨道数量减少、设计规则数量和复杂性增加以及严格的图案化规则，出现了更多布线问题。SOTA 标准单元框架虽然能够自动化完成版图，但在复杂的顺序单元设计中 PPA 仍然有困难。因此一个结合经验丰富人类设计师的专业知识，用于逐步优化单元版图的 PPA。高质量的器件聚类（device clustering）在版图规划中考虑了网表拓扑（netlist topology）、扩散共享/中断（diffusion sharing/break）和版图中的布线性（routability in the layouts），有助于找到更具竞争力的 PPA 和可布线版图。该论文利用 LLM 的自然语言和推理能力，逐步生成高质量的聚类约束，以优化单元版图的 PPA 并使用 ReAct 提示调试布线性。在 2 纳米的顺序标准单元基准测试中，证明了所提出的方法不仅可以将单元面积减小至多 19.4%，而且生成的 LVS/DRC 清洁单元版图比以往工作多出 23.5%。该论文综上布局成功平均减少 4.65% 单元面积，还能解决单元版图设计中布线问题。

---

15. **Towards LLM-Powered Verilog RTL Assistant: Self-Verification and Self-Correction** [paper](https://arxiv.org/abs/2406.00115)

_Hanxian Huang, Zhenghan Lin, Zixuan Wang, Xin Chen, Ke Ding and Jishen Zhao_

arXiv 2024

摘要：该论文探讨了使用 LLM 在生成高质量 RTL 代码，并将人为干扰降到最低。提出了一种用于 erilog RTL 设计工作流的 LLM 驱动编程助手。VeriAsset 将 RTL 设计描述作为输入，并使用相应的测试台生成高质量的 RTL 代码。通过采用自动提示系统，并在代码生成循环中集成 RTL 模拟器，VeriAsset 使 LLM 能够对生成的代码进行自我纠正和自我验证，以推理不同时间步骤的代码行为，最后它通过读取编译和模拟结果自我修正代码，生成最终的 RTL 代码，修正编译和模拟中的错误。该论文设计充分利用了 LLM 在多轮交互（multi-turn interaction）和思维链（chain-of-thought）推理方面的能力，以提高生成代码的质量。使用各种基准测试对 VeriAssist 进行评估，发现它在语法和功能正确性上都显著优于现有的 LLM 实现，从而最大限度地减少了人工干预，使 RTL 设计对新手更加容易接近。

---

16. **Domain-Adapted LLMs for VLSI Design and Verification: A Case Study on Formal Verification** [paper](https://ieeexplore.ieee.org/abstract/document/10538589)

_Mingjie Liu, Minwoo Kang, haith Bany Hamad, Syed Suhaib and Haoxing Ren_

VTS 2024

摘要：该论文提出将语言模型适配到 VLSI 设计领域方法，展现领域自适应模型 ChipNeMo 在 IC 设计和 EDA 基准测试中相对于类似规模更高的性能。最后该论文介绍了 LLM 应用于硬件形式验证的前景案例研究。实验表明最大和最强大的模型（e.g. GPT-4），能够生成语法正确的 SVA 实现，但在确保精确反映用户意图的高级自然语言描述的形式属性方面，仍有改进空间。

---

17. **The Dawn of AI-Native EDA: Promises and Challenges of Large Circuit Models** [paper](https://arxiv.org/abs/2403.07257)

_Chen, Lei and Chen, Yiqi and Chu, Zhufei and Fang, Wenji and Ho, Tsung-Yi and Huang, Yu and Khan, Sadaf and Li, Min and Li, Xingquan and Liang, Yun and others_

arXiv 2024

摘要：在电子设计自动化（EDA）领域内，AI 驱动的解决方案已经成为了强大的工具，但它们通常是增强而非重新定义现有方法。这些解决方案往往将来自其他领域如视觉、文本和图形分析的深度学习模型重新利用于电路设计，而没有针对电子电路的独特复杂性进行定制。这种“AI4EDA”方法未能实现全面的设计综合与理解，忽视了电路数据的电气、逻辑和物理方面的复杂相互作用。该论文主张从 AI4EDA 向 AI 原生 EDA 的范式转变，将 AI 整合到设计流程的核心。至关重要的是，该论文指出正在开发一种多模态电路表示学习技术，该技术通过协调和提取功能规格、RTL 设计、电路网表和物理布局等多种数据来源的洞察，以提供全面的理解。

该论文倡导创建本质上是多模态的大型电路模型（LCMs），这些模型被设计用来解码和表达电路数据的丰富语义和结构，从而促进更加弹性、高效和创新的设计方法。采纳这种 AI 原生理念，预见到一个超越当前 EDA 创新高原的轨迹，引发电子设计方法论的深刻“左转”。所设想的进步不仅预示着现有 EDA 工具的演变，而且是一场革命，催生了新型的设计工具，这些工具承诺将从根本上提高设计生产力，并开启一个新的时代，在这个时代中，电路性能、功率和面积（PPA）的优化不是逐步实现的，而是通过重新定义电子系统能力的基准的飞跃来实现的。

---

## References

- [https://github.com/Thinklab-SJTU/Awesome-LLM4EDA](https://github.com/Thinklab-SJTU/Awesome-LLM4EDA)
- [https://github.com/DfX-NYUAD/LLM4IC](https://github.com/DfX-NYUAD/LLM4IC)
- [https://ai4eda.github.io/](https://ai4eda.github.io/)

---

## Contact

Email：junjieli_1@163.com or lij850601@gmail.commailto:lij850601@gmail.com
