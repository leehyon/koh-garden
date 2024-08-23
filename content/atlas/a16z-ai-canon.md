---
title: AI 学习精选集
date: 2024-08-22
draft: true
tags:
  - ai
  - resource
---

本文档为一份详尽的 AI 学习资源指南，原英文由 a16z 整理。这些资源不需要专业背景，旨在帮助初学者和希望快速掌握现代 AI 重要概念的人士。它汇集了论文、博客文章、课程和指南，覆盖了 AI 领域的广泛主题，适合各类读者和学习者。通过这些资源，用户可以建立对机器学习和 AI 的基本理解，从深度学习的基础知识到大学级别的课程，帮助大家在这一快速发展的领域中跟上最新进展。

---

> Original: https://a16z.com/ai-canon/

## 简单介绍...

这些文章不需要特别的背景知识，可以帮助你快速了解现代 AI 领域最重要的部分。

- [Software 2.0](https://karpathy.medium.com/software-2-0-a64152b37c35): Andrej Karpathy 在 2017 年是最早清楚解释为什么新的 AI 浪潮真的很重要的人之一。他的论述是，AI 是一种新的强大的计算机编程方式。随着 LLMs 的快速改进，这一观点被证明是有远见的，并且为 AI 市场的发展提供了一个很好的心理模型。
- [State of GPT](https://build.microsoft.com/en-US/sessions/db3f4859-cd30-4445-a0cd-553c3304f8e2): 这也是 Karpathy 的作品，这是关于 ChatGPT/GPT 如何工作，如何使用它们，以及研发可能会走向何处的非常易懂的解释。
- [What is ChatGPT doing … and why does it work?](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/): 计算机科学家和企业家 Stephen Wolfram 从基本原理出发，给出了一个冗长但非常易读的解释，讲述了现代 AI 模型如何工作。他跟随时间线从早期的神经网络到今天的 LLMs 和 ChatGPT。
- [Transformers, explained](https://daleonai.com/transformers-explained): 这篇文章由 Dale Markowitz 撰写，简短而直接地回答了“LLM 是什么，如何工作？”，可以轻松了解该技术并形成直觉。尽管它是关于 GPT-3 写的，但仍适用于较新模型。
- [How Stable Diffusion works](https://mccormickml.com/2022/12/21/how-stable-diffusion-works/): 这是计算机视觉的类似物。Chris McCormick 给出了关于 Stable Diffusion 工作原理及一般文本生成图像模型的通俗解释。对于一个更加简单的介绍，请查看 StableDiffusion 版块的这个[漫画](https://www.reddit.com/r/StableDiffusion/comments/zs5dk5/i_made_an_infographic_to_explain_how_stable/)。

## 基础学习：神经网络、反向传播和嵌入

这些资源提供了对机器学习和 AI 基本概念的理解，从深度学习基础到 AI 专家的大学级课程。

### 解释者

- [Deep learning in a nutshell: core concepts](https://developer.nvidia.com/blog/deep-learning-nutshell-core-concepts/): Nvidia 的四部分系列，从 2015 年起介绍深度学习的基本知识，是任何刚开始了解 AI 的人都值得一看的资源。
- [Practical deep learning for coders](https://course.fast.ai/): 一个全面的免费课程，通过实际示例和代码解释 AI 的基础知识。
- [Word2vec explained](https://towardsdatascience.com/word2vec-explained-49c52b4ccb71): 对嵌入和标记的简单介绍，这些是 LLMs（和所有语言模型）的构建块。
- [Yes you should understand backprop](https://karpathy.medium.com/yes-you-should-understand-backprop-e2f06eab496b): 如果你想了解细节，这是一篇关于反向传播的更深入的文章。如果你还想了解更多，请尝试 [Stanford CS231n lecture](https://www.youtube.com/watch?v=i94OvYb6noo)在 YouTube 上的视频。

### 课程

- [Stanford CS229](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU): Andrew Ng 带你了解机器学习基础，介绍机器学习基础知识。
- [Stanford CS224N](https://www.youtube.com/playlist?list=PLoROMvodv4rOSH4v6133s9LFPRHjEmbmJ): Chris Manning 带你通过深度学习了解 NLP 基础知识，涉及到初代 LLMs。

## 技术深入：了解 Transformer 和大型模型

有无数的资源试图解释 LLMs 如何工作。以下是我们最喜欢的一些，面向各类读者和观众。

### 解释者

- [The illustrated transformer](https://jalammar.github.io/illustrated-transformer/): Jay Alammar 对 Transformer 架构的更技术性的概述。
- [The annotated transformer](http://nlp.seas.harvard.edu/annotated-transformer/): 如果你想在源代码层面了解 Transformer 的深入文章。需要一些 PyTorch 知识。
- [Let’s build GPT: from scratch, in code, spelled out](https://www.youtube.com/watch?v=kCc8FmEb1nY): 对于工程师而言，Karpathy 在视频中讲解了如何构建 GPT 模型。
- [The illustrated Stable Diffusion](https://jalammar.github.io/illustrated-stable-diffusion/: 嵌入扩散模型的介绍，最常见的图像生成 AI 模型。
- [RLHF: Reinforcement Learning from Human Feedback](https://huyenchip.com/2023/05/02/rlhf.html): Chip Huyen 解释了 RLHF，这可以使 LLMs 的行为更可预测和人性化。这是 ChatGPT 等系统中最重要但最不为人知的方面之一。
- [Reinforcement learning from human feedback](https://www.youtube.com/watch?v=hhiLw5Q_UFg): 计算机科学家和 OpenAI 联合创始人 John Shulman 在这个演讲中更深入地探讨了当前状态、进展和 LLMs 与 RLHF 的局限性。

### 课程

- [Stanford CS25](https://www.youtube.com/watch?v=P127jhj-8-Y): Transformers United，一套关于 Transformer 的在线研讨会。
- [Stanford CS324](https://stanford-cs324.github.io/winter2022/): 由 Percy Liang、Tatsu Hashimoto 和 Chris Re 教授的大型语言模型课程，涵盖了 LLMs 的很多技术和非技术方面。

### 参考和评论

- [Predictive learning, NIPS 2016](https://www.youtube.com/watch?v=Ount2Y4qxQo&t=1072s): 在这个早期的演讲中，Yann LeCun  强调了无监督学习作为大规模AI模型架构的重要元素。跳到[19:20](https://youtu.be/Ount2Y4qxQo?t=1160)看著名的蛋糕比喻，这仍然是现代 AI 的最佳心理模型之一。
- [AI for full-self driving at Tesla](https://www.youtube.com/watch?v=hx7BXih7zx8): Karpathy 的另一经典演讲，这次是关于特斯拉数据收集引擎的。从 [8:35](https://youtu.be/hx7BXih7zx8?t=515) 开始，是关于长尾问题（在这个案例中是停车标志检测）为什么这么难的伟大 AI 论述之一。
- [The scaling hypothesis](https://gwern.net/scaling-hypothesis): LLMs 最意想不到的方面之一是，扩展（添加更多数据和计算）一直在提高准确性。GPT-3 是第一个清楚展示这一点的模型，而 Gwern 的文章很好地解释了这一点背后的直觉。
- [Chinchilla’s wild implications](https://www.lesswrong.com/posts/6Fpvch8RR29qLEWNH/chinchilla-s-wild-implications): 名义上是对重要的 Chinchilla 论文的解释（见下文），这篇文章探讨了 LLM 扩展中的大问题：我们是否快要用尽数据？这建立在上文的基础上，提供了扩展法则的新视角。
- [A survey of large language models](https://arxiv.org/pdf/2303.18223v4.pdf): 对当前 LLMs 的全面分类，包括发展时间线、规模、训练策略、训练数据、硬件等。
- [Sparks of artificial general intelligence: Early experiments with GPT-4](https://arxiv.org/abs/2303.12712): Microsoft Research 对 GPT-4 的能力相对于人类智能的早期分析。
- [The AI revolution: How Auto-GPT unleashes a new era of automation and creativity](https://pub.towardsai.net/the-ai-revolution-how-auto-gpt-unleashes-a-new-era-of-automation-and-creativity-2008aa2ca6ae): 关于 Auto-GPT 和一般 AI 代理的介绍。这项技术非常早期但重要——它使用互联网访问和自生成的子任务来解决特定的复杂问题或目标。
- [The Waluigi Effect](https://www.lesswrong.com/posts/D7PumeYTDPfBTp3i7/the-waluigi-effect-mega-post): 名义上是对“ Waluigi 效应”（即，为什么“替身”会出现在 LLM 行为中）的解释，但主要有趣的是对 LLM 的提示理论的深入探讨。

## 实践指南：使用 LLMs 构建

一个新的应用堆栈正在以 LLMs 为核心出现。尽管在这一主题上还没有很多正式教育，但我们挑选了一些我们发现的最有用的资源。

### 参考

- [Build a GitHub support bot with GPT3, LangChain, and Python](https://dagster.io/blog/chatgpt-langchain): 现代 LLM 应用栈的最早期公共解释之一。虽然其中的一些建议已经过时，但在很多方面它开启了新 AI 应用的广泛采用和实验。
- [Building LLM applications for production](https://huyenchip.com/2023/04/11/llm-engineering.html): Chip Huyen 讨论了构建 LLM 应用的许多主要挑战，如何解决这些问题，以及哪些类型的用例最有意义。
- [Prompt Engineering Guide](https://www.promptingguide.ai/): 对于任何撰写 LLM 提示的人（包括应用开发人员），这是最全面的指南，包含一些流行模型的具体示例。对于更轻松、更对话式的处理方式，请尝试 [Brex 的提示工程指南](https://github.com/brexhq/prompt-engineering)。
- [Prompt injection: What’s the worst that can happen?](https://simonwillison.net/2023/Apr/14/worst-that-can-happen/): 提示注入是 LLM 应用中潜在的严重安全漏洞，目前尚无完美解决方案。Simon Willison 在这篇文章中给出了对此问题的权威描述。几乎 Simon 在 AI 上撰写的所有内容都很出色。
- [OpenAI cookbook](https://github.com/openai/openai-cookbook/tree/main): 对于开发人员来说，这是 OpenAI API 工作的权威指南和代码示例的集合。它不断更新新的代码示例。
- [Pinecone learning center](https://www.pinecone.io/learn/): 许多 LLM 应用基于向量搜索模式。尽管 Pinecone 的学习中心是品牌供应商内容，但它提供了一些最有用的关于如何在此模式下构建的教学。
- [LangChain docs](https://python.langchain.com/en/latest/index.html): 作为 LLM 应用的默认编排层，LangChain 连接到几乎所有其他堆栈部分。因此他们的文档是真正参考整个栈及其各组成部分如何结合的。

### 课程

- [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/): 由 Charles Frye、Sergey Karayev 和 Josh Tobin 教授的关于构建 LLM 基础应用的实用课程。
- [Hugging Face Transformers](https://huggingface.co/learn/nlp-course/chapter1/1): 使用 Hugging Face transformers 库中的开源 LLM 指南。

### LLM基准

- [Chatbot Arena](https://lmsys.org/blog/2023-05-03-arena/): UC Berkeley 团队领导的流行 LLMs 的 Elo 排名系统。用户还可以通过头对头比较模型参与其中。
- [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard): Hugging Face 的排名，比较了开源 LLM 在许多基准和任务上的表现。

## 市场分析

我们都惊叹于生成 AI 的产出，但仍有许多问题尚待解答。哪些产品和公司将生存并发展？艺术家将何去何从？公司应如何利用它？它将如何影响实际工作和整个社会？以下是一些尝试回答这些问题的文章。

### a16z 思考

- [Who owns the generative AI platform?](https://a16z.com/who-owns-the-generative-ai-platform/): 我们对价值在生成 AI 基础设施、模型和应用层面积累及可能积累的旗舰评估。
- [Navigating the high cost of AI compute](https://a16z.com/2023/04/27/navigating-the-high-cost-of-ai-compute/): 详细分析了为什么生成 AI 模型需要如此多的计算资源，以及如何在高需求市场中获得这些资源（即合适的 GPU、合适的数量、合适的成本）。
- [Art isn’t dead, it’s just machine-generated](https://a16z.com/art-isnt-dead-its-just-machine-generated/): 看看 AI 模型如何能够重新定义创意领域——通常被认为是最后一个抵御自动化的阵地——远快于软件开发等领域。
- [The generative AI revolution in games](https://a16z.com/the-generative-ai-revolution-in-games/): 我们的游戏团队详尽分析了生成高细节图形的能力将如何改变游戏设计师、工作室和整个市场的运作方式。 [这个后续文章](https://a16z.com/the-generative-ai-revolution-will-enable-anyone-to-create-games/) 从我们的游戏团队看了 AI 生成内容相对于用户生成内容的出现。
- [For B2B generative AI apps, is less more?](https://a16z.com/for-b2b-generative-ai-apps-is-less-more/): 预测了 LLMs 将在 B2B 企业应用中如何演变，围绕总结信息的理念最为有价值。
- [Financial services will embrace generative AI faster than you think](https://a16z.com/2023/04/19/financial-services-will-embrace-generative-ai-faster-than-you-think/): 认为金融服务业将迅速采用生成 AI，以提供个性化消费者体验、成本效益高的运营、更好的合规性、改进的风险管理和动态预测和报告。
- [Generative AI: The next consumer platform](https://a16z.com/generative-ai-the-next-consumer-platform/): 分析了生成 AI 如何跨多个领域影响消费者市场，从治疗到电子商务。
- [To make a real difference in health care, AI will need to learn like we do](https://time.com/6274752/ai-health-care/): AI 将不可逆转地改变我们预防和治疗疾病的方式。然而，要真正改变药物发现和医疗，上学习。

## 里程碑式研究结果

我们今天看到的许多惊人 AI 产品都是由专家在大公司和领先大学内部进行的同样惊人的研究成果。最近，我们也看到了个人和开源社区的令人印象深刻的工作，他们将热门项目带入新的方向，例如创建自动化代理或将模型移植到更小的硬件上。

以下是许多这些论文和项目的集合，适合那些真正想深入研究生成AI的读者。对于研究论文和项目，我们还包括了附带的博客文章或网站链接（如有），这些往往能在更高层次上解释这些研究。而且我们还包括了最早的发表年份，这样你可以跟踪基础研究随时间的发展。

### 大语言模型

#### 新模型

- [Attention is all you need](https://arxiv.org/abs/1706.03762) (2017)：Google Brain 的开创性 Transformer 研究论文，奠定了现代 AI 模型的基础。([blog post](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html))
- [BERT: pre-training of deep bidirectional transformers for language understanding](https://arxiv.org/abs/1810.04805) (2018)：首批公开发布的大型语言模型之一，至今仍有多种变体在使用。([blog post](https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html))
- [Improving language understanding by generative pre-training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (2018)：OpenAI 首次介绍 GPT 架构的论文，该架构已成为 LLM 的主要发展路径。([blog post](https://openai.com/research/language-unsupervised))
- [Language models are few-shot learners](https://arxiv.org/abs/2005.14165) (2020)：OpenAI 描述 GPT-3 及其只使用解码器架构的大型语言模型的论文。
- [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155) (2022)：OpenAI 介绍 InstructGPT 的论文，该模型利用人为反馈来训练，从而能更好地遵循提示中的指令。这是使 LLMs 对消费者更友好的关键点之一。([blog post](https://openai.com/research/instruction-following))
- [LaMDA: language models for dialog applications](https://arxiv.org/abs/2201.08239) (2022)：Google 推出的专为人与聊天机器人之间的自由对话而设计的模型，适用于各类话题。([blog post](https://blog.google/technology/ai/lamda/))
- [PaLM: Scaling language modeling with pathways](https://arxiv.org/abs/2204.02311) (2022)：Google 的 PaLM 模型，采用新的系统在数千个芯片上训练 LLMs，并展示了随着模型规模扩大在某些任务上的更大改进。([blog post](https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html))。还可以查看[PaLM-2技术报告](https://arxiv.org/abs/2305.10403)。
- [OPT: Open Pre-trained Transformer language models](https://arxiv.org/abs/2205.01068) (2022)：OPT 是性能最佳的完全开源 LLM 之一。这个 1750 亿参数模型的发布代码已在公开数据集上进行训练。([blog post](https://ai.facebook.com/blog/democratizing-access-to-large-scale-language-models-with-opt-175b/))
- [Training compute-optimal large language models](https://arxiv.org/abs/2203.15556) (2022)：Chinchilla 论文。它提出大多数模型受限于数据而不是计算能力，并改变了 LLM 规模化的共识。([blog post](https://www.deepmind.com/blog/an-empirical-analysis-of-compute-optimal-large-language-model-training))
- [GPT-4 technical report](https://arxiv.org/abs/2303.08774) (2023)：OpenAI 最新最重要的论文，以其披露的信息少而著称！([blog post](https://openai.com/research/gpt-4))。[GPT-4系统报告](https://cdn.openai.com/papers/gpt-4-system-card.pdf)揭示了 OpenAI 如何处理幻觉、隐私、安全等问题。
- [LLaMA: Open and efficient foundation language models](https://arxiv.org/abs/2302.13971) (2023)：Meta 推出的模型，几乎开启了一场开源 LLM 革命。与许多最佳闭源模型竞争，但仅对研究人员开放使用。([blog post](https://ai.facebook.com/blog/large-language-model-llama-meta-ai/))
- [Alpaca: A strong, replicable instruction-following model](https://crfm.stanford.edu/2023/03/13/alpaca.html) (2023)：出自斯坦福，该模型展示了指令调优的力量，尤其是在开源小型模型中，相较于单纯的规模化更有效。

#### 模型改进（如微调、检索、注意力）

- [Deep reinforcement learning from human preferences](https://proceedings.neurips.cc/paper_files/paper/2017/file/d5e2c0adad503c91f91df240d0cd4e49-Paper.pdf) (2017)：在游戏和机器人领域进行强化学习研究，结果证明是 LLMs 的一个绝佳工具。
- [Retrieval-augmented generation for knowledge-intensive NLP tasks](https://arxiv.org/abs/2005.11401) (2020)：由 Facebook 开发的 RAG 是通过信息检索提高 LLM 准确性的两条主要研究路径之一。([blog post](https://ai.facebook.com/blog/retrieval-augmented-generation-streamlining-the-creation-of-intelligent-natural-language-processing-models/))
- [Improving language models by retrieving from trillions of tokens](https://arxiv.org/abs/2112.04426) (2021)：RETRO，即“Retrieval Enhanced TRansfOrmers”，是另一个提高 LLM 准确性的方法——由 DeepMind 开发，通过访问不包含在训练数据中的信息来实现。([blog post](https://www.deepmind.com/blog/improving-language-models-by-retrieving-from-trillions-of-tokens))
- [LoRA: Low-rank adaptation of large language models](https://arxiv.org/abs/2106.09685) (2021)：微软的这项研究引入了一种更高效的替代微调方法，用于在新数据上训练 LLMs。它现在已经成为社区微调的标准，特别是对于图像模型。
- [Constitutional AI](https://arxiv.org/abs/2212.08073) (2022)：Anthropic 团队引入的来自 AI 反馈的强化学习（RLAIF）概念。主要思想是我们可以在其他 AI 监督下开发无害的AI助手。
- [FlashAttention: Fast and memory-efficient exact attention with IO-awareness](https://arxiv.org/abs/2205.14135) (2022)：斯坦福的这项研究为最先进的模型理解更长的文本序列（及更高分辨率的图像）打开了大门，而无需高昂的训练时间和成本。([blog post](https://ai.stanford.edu/blog/longer-sequences-next-leap-ai/))
- [Hungry hungry hippos: Towards language modeling with state space models](https://arxiv.org/abs/2212.14052) (2022)：同样来自斯坦福，这篇论文描述了语言建模中注意力的主要替代方案之一。这是更好扩展和训练效率的一个有前途的途径。([blog post](https://hazyresearch.stanford.edu/blog/2023-01-20-h3))

### 图像生成模型

- [Learning transferable visual models from natural language supervision](https://arxiv.org/abs/2103.00020) (2021)：介绍基础模型 CLIP 的论文，该模型将文本描述与图像联系起来。首次在计算机视觉中有效大规模使用基础模型。([blog post](https://openai.com/research/clip))
- [Zero-shot text-to-image generation](https://arxiv.org/abs/2102.12092) (2021)：介绍 DALL-E 的论文，该模型结合了上面提到的 CLIP和 GPT-3，根据文本提示自动生成图像。其继任者 DALL-E 2 将在 2022 年引发基于图像的生成AI热潮。([blog post](https://openai.com/research/dall-e))
- [High-resolution image synthesis with latent diffusion models](https://arxiv.org/abs/2112.10752) (2021)：描述 Stable Diffusion 的论文，该模型在推出和迅速增长的开源社区后详细介绍。
- [Photorealistic text-to-image diffusion models with deep language understanding](https://arxiv.org/abs/2205.11487) (2022)：Imagen 是 Google 在 AI 图像生成领域的探索。自发布以来，超过一年后，该模型尚未公开发布。([website](https://imagen.research.google/))
- [DreamBooth: Fine tuning text-to-image diffusion models for subject-driven generation](https://arxiv.org/abs/2208.12242) (2022)：由 Google 开发的系统 DreamBooth，用于训练模型识别用户提交的主题并将其应用于提示的上下文中（如“微笑着站在埃菲尔铁塔前”）。([website](https://dreambooth.github.io/))
- [Adding conditional control to text-to-image diffusion models](https://arxiv.org/abs/2302.05543) (2023)：这篇斯坦福论文介绍了 ControlNet，一款现在非常流行的工具，允许对嵌入扩散模型进行细粒度控制以生成图像。

### 智能代理
- [A path towards autonomous machine intelligence](https://openreview.net/pdf?id=BZ5a1r-kVsf) (2022)：Meta AI 负责人和纽约大学教授 Yann LeCun 提出的关于如何构建真正理解周围世界的自主智能代理的建议。
- [ReAct: Synergizing reasoning and acting in language models](https://arxiv.org/abs/2210.03629) (2022)：普林斯顿和 Google 的项目，测试和改进 LLMs 的推理和规划能力。([blog post](https://ai.googleblog.com/2022/11/react-synergizing-reasoning-and-acting.html))
- [Generative agents: Interactive simulacra of human behavior](https://arxiv.org/abs/2304.03442) (2023)：斯坦福和 Google 的研究人员使用 LLMs 驱动智能代理，环境类似于“The Sims”，交互是自然产生的而不是编程的。
- [Reflexion: an autonomous agent with dynamic memory and self-reflection](https://arxiv.org/abs/2303.11366) (2023)：东北大学和麻省理工学院研究人员的工作，通过让 LLMs 从错误和过去经验中学习，解决问题更加可靠。
- [Toolformer: Language models can teach themselves to use tools](https://arxiv.org/abs/2302.04761) (2023)：Meta 的这个项目训练了 LLMs 使用外部工具（例如指向搜索引擎和计算器的 API），以在不增加模型规模的情况下提高准确性。
- [Auto-GPT: An autonomous GPT-4 experiment](https://github.com/Significant-Gravitas/Auto-GPT)：一个开源实验，通过给予工具（互联网访问、文件存储等）扩展 GPT-4 的能力，并选择使用哪些工具来解决特定任务。
- [BabyAGI](https://github.com/yoheinakajima/babyagi)：这个 Python 脚本利用 GPT-4 和向量数据库（存储上下文），以计划并执行一系列任务来解决更广泛的目标。

### 其他数据模态

#### 代码生成

- [Evaluating large language models trained on code](https://arxiv.org/abs/2107.03374) (2021)：这是 OpenAI 关于 Codex 的研究论文，Codex 是 GitHub Copilot 产品背后的代码生成模型。([blog post](https://openai.com/blog/openai-codex))
- [Competition-level code generation with AlphaCode](https://www.science.org/stoken/author-tokens/ST-905/full) (2021)：DeepMind 的这项研究展示了一种模型，能够编写比人类程序员更好的代码。([blog post](https://www.deepmind.com/blog/competitive-programming-with-alphacode))
- [CodeGen: An open large language model for code with multi-turn program synthesis](https://arxiv.org/abs/2203.13474) (2022)：来自 Salesforce AI 研究部门的 CodeGen，目前支撑着 Replit Ghostwriter 的代码生成产品。([blog post](https://blog.salesforceairesearch.com/codegen/))

#### 视频生成

- [Make-A-Video: Text-to-video generation without text-video data](https://arxiv.org/abs/2209.14792) (2022)：Meta 模型，根据文本提示创建短视频，还可以为静态图片添加运动或创建现有视频的变体。([blog post](https://makeavideo.studio/))
- [Imagen Video: High definition video generation with diffusion models](https://arxiv.org/abs/2210.02303) (2022)：顾名思义：Google 基于图像的 Imagen 模型版本，优化以根据文本提示生成短视频。([website](https://imagen.research.google/video/))

#### 人类生物学和医学数据

- [Strategies for pre-training graph neural networks](https://arxiv.org/pdf/1905.12265.pdf) (2020)：这项出版物奠定了用于药物发现应用（如分子属性预测和蛋白质功能预测）的有效预训练方法的基础。([blog post](https://snap.stanford.edu/gnn-pretrain/))
- [Improved protein structure prediction using potentials from deep learning](https://www.nature.com/articles/s41586-019-1923-7) (2020)：DeepMind 的以蛋白质为中心的 Transformer 模型 AlphaFold，使得从序列预测蛋白质结构成为可能——这一真正的突破已经对理解生物过程和开发新疗法产生了深远影响。([blog post](https://www.deepmind.com/blog/alphafold-a-solution-to-a-50-year-old-grand-challenge-in-biology)) ([explainer](https://www.blopig.com/blog/2021/07/alphafold-2-is-here-whats-behind-the-structure-prediction-miracle/))
- [Large language models encode clinical knowledge](https://arxiv.org/abs/2212.13138) (2022)：Med-PaLM 是一种能够正确回答美国医学执照考试风格问题的大型语言模型。自那以后，团队已经发布了 Med-PaLM2 的性能结果，后者的得分与“专家”考生相当。其他团队进行了类似的实验 [ChatGPT](https://www.medrxiv.org/content/10.1101/2022.12.19.22283643v2) 和 [GPT-4](https://arxiv.org/abs/2303.13375)。( [video](https://www.youtube.com/watch?v=saWEFDRuNJc) )

#### 音频生成

- [Jukebox: A generative model for music](https://arxiv.org/abs/2005.00341) (2020)：OpenAI 在音乐生成领域的尝试，使用 Transformer，能够生成音乐、声乐和歌词，所需训练极少。([blog post](https://openai.com/research/jukebox))
- [AudioLM: a language modeling approach to audio generation](https://arxiv.org/pdf/2209.03143.pdf) (2022)：AudioLM 是 Google 的一个项目，用于生成多种音频，包括语音和乐器。([blog post](https://ai.googleblog.com/2022/10/audiolm-language-modeling-approach-to.html))
- [MusicLM: Generating music from text](https://arxiv.org/abs/2301.11325) (2023)：当前基于 AI 的音乐生成领域的最先进状态，显示出更高的质量和一致性，相比以往的尝试。([blog post](https://google-research.github.io/seanet/musiclm/examples/))

#### 多维图像生成

- [NeRF: Representing scenes as neural radiance fields for view synthesis](https://arxiv.org/abs/2003.08934) (2020)：加州大学伯克利分校主导的团队研究了如何使用 5D 坐标“合成复杂场景的新颖视图”。([website](https://www.matthewtancik.com/nerf))
- [DreamFusion: Text-to-3D using 2D diffusion](https://arxiv.org/pdf/2209.14988.pdf) (2022)：Google 和加州大学伯克利分校的研究人员以 NeRF 为基础，从 2D 输入生成 3D 图像。([website](https://dreamfusion3d.github.io/))
