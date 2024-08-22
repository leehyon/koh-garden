---
title: AI Canon from a16z
date: 2024-08-22
draft: true
tags:
  - ai
  - resource
---

本文档为一份详尽的 AI 学习资源指南，原英文由 a16z 整理。这些资源不需要专业背景，旨在帮助初学者和希望快速掌握现代 AI 重要概念的人士。它汇集了论文、博客文章、课程和指南，覆盖了 AI 领域的广泛主题，适合各类读者和学习者。通过这些资源，用户可以建立对机器学习和 AI 的基本理解，从深度学习的基础知识到大学级别的课程，帮助大家在这一快速发展的领域中跟上最新进展。

> Original: https://a16z.com/ai-canon/ 

人工智能研究正在以指数级的速度增长。对于 AI 专家来说，很难跟上所有新出版的内容，更不用说新手了，他们不知道从哪里开始。  

因此，在这篇文章中，我们分享了我们依靠这些资源来了解现代人工智能的精选列表。我们称之为“AI 圣经”，因为这些论文、博客文章、课程和指南在过去几年对这个领域产生了巨大的影响。  
 我们先从介绍 Transformer 和潜在扩散模型开始，这些模型正在推动当前的人工智能浪潮。然后我们深入探讨技术学习资源；使用大型语言模型 LLM 构建的实用指南；以及对人工智能市场的分析。最后，我们包括了“Attention is All You Need”——谷歌在 2017 年发表的一篇论文，该论文向世界介绍了 Transformer 模型，并开启了生成式人工智能的时代。  
## 友好的引言

这些文章不需要专门的背景知识，可以帮助你快速了解现代人工智能浪潮中最重要的一部分。

- [Software 2.0](https://karpathy.medium.com/software-2-0-a64152b37c35): Andrej Karpathy 是最早清楚解释（在 2017 年！）为什么新一波人工智能真正重要的少数人之一。他的论点是，人工智能是一种新的、强大的编程计算机的方法。随着大型语言模型的迅速改进，这一理论已经证明了其预见性，并为人工智能市场可能的发展提供了一个良好的心理模型。
- [State of GPT](https://build.microsoft.com/en-US/sessions/db3f4859-cd30-4445-a0cd-553c3304f8e2): 也来自 Karpathy，这是一个非常易于理解的解释 ChatGPT、一般 GPT 模型的工作原理，如何使用它们以及研究和开发可能采取的方向是什么。
- [What is ChatGPT doing … and why does it work?](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/): 计算机科学家兼企业家 Stephen Wolfram 从第一原则出发，对现代人工智能模型是如何工作的给出了一个长而易读的解释。他遵循从早期神经网络到今天的 LLM 和 ChatGPT 的时间线。
- [Transformers, explained](https://daleonai.com/transformers-explained): Dale Markowitz 的这篇文章是对“什么是 LLM，它是如何工作的？”这个问题的一个简短、直接的回答。这是进入这个话题并发展对该技术的理解的好方法。它写的是 GPT-3，但仍然适用于更先进的模型。
- [How Stable Diffusion works](https://mccormickml.com/2022/12/21/how-stable-diffusion-works/): 这与上一篇文章的计算机视觉类似。Chris McCormick 对 Stable Diffusion 的工作原理进行了非专业人士的解释，并围绕文本到图像模型培养直觉。对于更简单的介绍，请查看 r/StableDiffusion 上的[漫画](https://www.reddit.com/r/StableDiffusion/comments/zs5dk5/i_made_an_infographic_to_explain_how_stable/)。

## 基础学习：神经网络、反向传播和嵌入 

这些资源为机器学习和人工智能的基本概念提供了一个基础理解，从深度学习的基础到 AI 专家的大学课程。  
### 解释者

- [Deep learning in a nutshell: core concepts](https://developer.nvidia.com/blog/deep-learning-nutshell-core-concepts/): Nvidia 的四部分系列文章介绍了 2015 年实践中的深度学习基础知识，对于刚刚开始了解人工智能的人来说是一个很好的资源。
- [Practical deep learning for coders](https://course.fast.ai/): 全面、免费的人工智能基础课程，通过实际例子和代码进行解释。
- [Word2vec explained](https://towardsdatascience.com/word2vec-explained-49c52b4ccb71): 易于理解的嵌入和 Token 介绍，它们是LLM（以及所有语言模型）的基础。
- [Yes you should understand backprop](https://karpathy.medium.com/yes-you-should-understand-backprop-e2f06eab496b): 对反向传播更深入的介绍。如果你还想了解更多，可以尝试在YouTube上观看斯坦福大学 [CS231n](https://www.youtube.com/watch?v=i94OvYb6noo) 讲座。
### 课程

- [Stanford CS229](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU): Andrew Ng 介绍机器学习，涵盖机器学习的基本知识。
- [Stanford CS224N](https://www.youtube.com/playlist?list=PLoROMvodv4rOSH4v6133s9LFPRHjEmbmJ): Chris Manning 的深度学习中的自然语言处理，通过第一代 LLM 介绍自然语言处理基础知识。

## 技术深度剖析：理解 Transformer 和大模型  

 有无数的资源试图解释 LLM 的工作原理。以下是我们的最爱，针对各种读者/观众。  
### 解释者

- [The illustrated transformer](https://jalammar.github.io/illustrated-transformer/): Jay Alammar对 Transformer 架构的更技术概述。
- [The annotated transformer](http://nlp.seas.harvard.edu/annotated-transformer/): 如果你想在源代码级别理解 Transformer，这是一个深入的文章。需要一些 PyTorch 知识。
- [Let’s build GPT: from scratch, in code, spelled out](https://www.youtube.com/watch?v=kCc8FmEb1nY): 对于那些工程师来说，Karpathy 做了一个视频演示如何构建一个 GPT 模型。
- [The illustrated Stable Diffusion](https://jalammar.github.io/illustrated-stable-diffusion/): 介绍潜在扩散模型，最常见的图像生成人工智能模型类型。
- [RLHF: Reinforcement Learning from Human Feedback](https://huyenchip.com/2023/05/02/rlhf.html): Chip Huyen 解释了 RLHF，这可以使 LLMs 的行为更加可预测和人性化。这是 ChatGPT 等系统中最重要但最不被理解的部分之一。
- [Reinforcement learning from human feedback](https://www.youtube.com/watch?v=hhiLw5Q_UFg): 计算机科学家、OpenAI 联合创始人 John Shulman 在这场精彩的演讲中深入探讨了当前状态、进展和 LLM 的局限性与 RLHF 相结合。  

### 课程

- [Stanford CS25](https://www.youtube.com/watch?v=P127jhj-8-Y): Transformer 联合，关于 Transformer 的在线研讨会。
- [Stanford CS324](https://stanford-cs324.github.io/winter2022/): 大语言模型与 Percy Liang、Tatsu Hashimoto 和 Chris Re，涵盖大语言模型广泛的技术和非技术方面。 
### 参考和评论

- [Predictive learning, NIPS 2016](https://www.youtube.com/watch?v=Ount2Y4qxQo&t=1072s): 在这次早期演讲中，Yann LeCun 为大规模人工智能模型架构中的无监督学习提出了强有力的论据。跳到 [19:20](https://youtu.be/Ount2Y4qxQo?t=1160) 处可以听到著名的蛋糕类比，这仍然是现代人工智能的最好心理模型之一。
- [AI for full-self driving at Tesla](https://www.youtube.com/watch?v=hx7BXih7zx8): 这次是 Karpathy 的经典演讲，这一次他介绍了特斯拉的数据收集引擎。从 [8:35](https://youtu.be/hx7BXih7zx8?t=515) 开始是一段伟大的 AI 咆哮，解释了为什么长尾问题（例如停车标志检测）如此困难。
- [The scaling hypothesis](https://gwern.net/scaling-hypothesis): 大语言模型最令人惊讶的特点之一就是规模（增加更多数据和计算）会提高准确性。GPT-3 是第一个清楚地展示这一点的模型，并且 Gwern 的文章很好地解释了背后的直觉。
- [Chinchilla’s wild implications](https://www.lesswrong.com/posts/6Fpvch8RR29qLEWNH/chinchilla-s-wild-implications): 名义上是对重要论文—— Chinchilla 的解释（见下文），这篇文章触及了大型语言模型规模的关键问题：我们是否已经用尽了数据？它建立在上面的文章之上，提供了一个关于规模定律的新视角。
- [A survey of large language models](https://arxiv.org/pdf/2303.18223v4.pdf): 当前大型语言模型的全面分解，包括开发时间线、大小、训练策略、训练数据、硬件等。
- [Sparks of artificial general intelligence: Early experiments with GPT-4](https://arxiv.org/abs/2303.12712): 微软研究院对 GPT-4 的能力进行了早期分析，这是目前最先进的大型语言模型，相对人类智能而言。
- [The AI revolution: How Auto-GPT unleashes a new era of automation and creativity](https://pub.towardsai.net/the-ai-revolution-how-auto-gpt-unleashes-a-new-era-of-automation-and-creativity-2008aa2ca6ae): 介绍Auto-GPT和一般人工智能代理。这项技术还处于非常早期阶段但非常重要，它使用互联网访问和自动生成子任务来解决特定、复杂的难题或目标。
- [The Waluigi Effect](https://www.lesswrong.com/posts/D7PumeYTDPfBTp3i7/the-waluigi-effect-mega-post): 名义上是对“瓦鲁伊效应”的解释（即为什么“双重人格”出现在大型语言模型的行为中），但它更有趣的是对大型语言模型提示理论的深入探讨。 

## 使用 LLM 构建的实用指南

 一个新的应用程序堆栈正在出现，以 LLM 为核心。虽然目前还没有很多关于这个主题的正式教育，但我们整理了一些我们发现的最有用的资源。  
### 参考

- [Build a GitHub support bot with GPT3, LangChain, and Python](https://dagster.io/blog/chatgpt-langchain): 现代LLM应用程序堆栈的最早公开解释之一。其中的一些建议已经过时，但许多方面它开启了广泛采用和新人工智能应用程序实验的新趋势。
- [Building LLM applications for production](https://huyenchip.com/2023/04/11/llm-engineering.html): Chip Huyen 讨论了许多在构建 LLM 应用程序时的关键挑战，如何应对它们以及哪些用例最合理。
- [Prompt Engineering Guide](https://www.promptingguide.ai/): 对于任何编写LLM提示的人——包括应用程序开发人员——这是最全面的指南，其中包括针对几种流行模型的具体示例。要获得更轻量级且更具对话性的处理方式，请尝试 [Brex’s prompt engineering guide](https://github.com/brexhq/prompt-engineering)。
- [Prompt injection: What’s the worst that can happen?](https://simonwillison.net/2023/Apr/14/worst-that-can-happen/) 提示注入是潜伏于LLM应用程序中的潜在严重安全漏洞，目前还没有完美的解决方案。Simon Willison在这篇文章中给出了这个问题的最终描述。Simon关于人工智能的所有写作都是杰出的。
- [OpenAI cookbook](https://github.com/openai/openai-cookbook/tree/main): 对于开发者来说，这是一本涵盖与OpenAI API交互的指导和代码示例的终极集合。它不断更新新的代码示例。
- [Pinecone learning center](https://www.pinecone.io/learn/): 许多LLM应用程序都基于矢量搜索范式。尽管Pinecone的学习中心被品牌为供应商内容，但它提供了有关在此模式下构建最有用的指令。
- [LangChain docs](https://python.langchain.com/en/latest/index.html): 作为LLM应用程序默认的编排层，LangChain连接到整个堆栈的几乎所有其他部分。因此，他们的文档是对整个堆栈及其组件如何组合在一起的真实参考。  

### 课程  

- [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/): 与查尔斯·弗莱、谢尔盖·卡雷耶夫和乔什·托宾一起学习如何使用基于 LLM 的应用程序。
- [Hugging Face Transformers](https://huggingface.co/learn/nlp-course/chapter1/1): 使用 Hugging Face Transformer 库中的开源 LLM。

### LLM 对比

- [Chatbot Arena](https://lmsys.org/blog/2023-05-03-arena/): 由加州大学伯克利分校的一支团队领导的流行的LLM排名系统。用户也可以通过一对一对比模型来参与其中。
- [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard): Hugging Face的一项排名，比较了开源LLM在一系列标准基准和任务上的表现。  

## 市场分析 

 我们所有人都惊叹于生成式人工智能可以生产出什么，但仍然有很多关于它意味着什么的问题。哪些产品和公司会生存下来并蓬勃发展？艺术家会发生什么事？企业应该如何使用它？它将如何影响就业和个人社会？以下是尝试回答这些问题的一些努力。  
### a16z 思考

- [Who owns the generative AI platform?](https://a16z.com/who-owns-the-generative-ai-platform/): 我们的旗舰评估，即在基础设施、模型和应用层面上，价值在哪里积累，并可能在未来积累。
- [Navigating the high cost of AI compute](https://a16z.com/2023/04/27/navigating-the-high-cost-of-ai-compute/): 详细分析为什么生成式AI模型需要如此多的计算资源，以及如何思考获取这些资源（即正确的GPU，在正确的价格下）的方法，在一个需求旺盛的市场中。
- [Art isn’t dead, it’s just machine-generated](https://a16z.com/art-isnt-dead-its-just-machine-generated/): 从我们对创意领域的重塑来看，人工智能模型比软件开发等其他领域更快地改变了创意领域——通常被认为是自动化最后的堡垒。
- [The generative AI revolution in games](https://a16z.com/the-generative-ai-revolution-in-games/): 来自我们游戏团队的一份深入分析，探讨了生成式AI能力如何改变游戏设计师、工作室和整个市场的运作方式。[本篇后续文章](https://a16z.com/the-generative-ai-revolution-will-enable-anyone-to-create-games/) 来自我们的游戏团队，重点关注人工智能生成内容与用户生成内容之间的关系。
- [For B2B generative AI apps, is less more?](https://a16z.com/for-b2b-generative-ai-apps-is-less-more/): 预测大型语言模型在企业级应用程序世界中的演变趋势，围绕着总结信息最终将比产生文本更有价值的想法。
- [Financial services will embrace generative AI faster than you think](https://a16z.com/2023/04/19/financial-services-will-embrace-generative-ai-faster-than-you-think/): 一项论点认为，金融服务行业正准备使用生成式AI来提供个性化消费者体验、高效运营、更好的合规性、改进的风险管理、动态预测和报告。
- [Generative AI: The next consumer platform](https://a16z.com/generative-ai-the-next-consumer-platform/): 从治疗到电子商务等一系列行业的机会，探讨生成式AI如何影响消费者市场。
- [To make a real difference in health care, AI will need to learn like we do](https://time.com/6274752/ai-health-care/): 人工智能即将从根本上改变我们预防和治疗疾病的方式。然而，为了真正转变药物发现到护理交付，我们应该投资于创建一个由“专家”人工智能组成的生态系统——它们的学习方式就像今天的最佳医生和药物开发商一样。
- [The new industrial revolution: Bio x AI](https://a16z.com/2023/05/17/the-new-industrial-revolution-bio-x-ai/): 人类历史上下一波工业革命将是生物学与人工智能相结合。  

### 其他观点  

- [On the opportunities and risks of foundation models](https://arxiv.org/abs/2108.07258): 斯坦福大学关于基础模型的概述论文。长篇大论，但这是术语的基础。
- [State of AI Report](https://www.stateof.ai/): 每年对人工智能领域的一切进行总结，包括技术突破、行业发展、政治/监管、经济影响、安全性和对未来预测。
- [GPTs are GPTs: An early look at the labor market impact potential of large language models](https://arxiv.org/abs/2303.10130): 来自OpenAI、OpenResearch和宾夕法尼亚大学的研究人员撰写的这篇论文预测，“大约有80％的美国劳动力可能会受到大型语言模型引入至少10％的工作任务的影响，而约19％的工人可能看到至少50％的任务受到影响。”
- [Deep medicine: How artificial intelligence can make healthcare human again](https://www.amazon.com/Deep-Medicine-Eric-Topol-audiobook/dp/B07PJ21V5N/ref=sr_1_1?hvadid=580688888836&hvdev=c&hvlocphy=9031955&hvnetw=g&hvqmt=e&hvrand=13698160037271563598&hvtargid=kwd-646099228782&hydadcr=15524_13517408&keywords=eric+topol+deep+medicine&qid=1684965845&sr=8-1): 如何让人工智能使医疗保健再次人性化：Eric Topol博士揭示了人工智能如何有可能解放医生从那些妨碍人与人之间联系的时间消耗型任务中解脱出来。医患关系得以恢复。 ([a16z podcast](https://a16z.com/podcast/a16z-podcast-ai-and-your-doctor-today-and-tomorrow/))

### 里程碑式的研究成果  

 我们今天看到的大部分令人惊叹的人工智能产品都是由大型公司和领先大学内部专家进行的研究的结果，这些研究本身也相当惊人。最近我们还看到了个人和开源社区在将流行项目引入新方向方面取得的出色工作，例如创建自动代理或将其模型移植到更小的硬件上。  
 这里收集了其中许多论文和项目，供那些真正想深入研究生成式人工智能的人使用。（对于研究论文和项目，我们还提供了博客文章或网站的链接，这些链接通常会以更高的水平解释事情。而且我们也包括了原始出版年份，以便您跟踪基础研究随着时间的变化。）  
### 大型语言模型  
###  新模型 

- [Attention is all you need](https://arxiv.org/abs/1706.03762) (2017): The original transformer work and research paper from Google Brain that started it all. ([blog post](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html))
- [BERT: pre-training of deep bidirectional transformers for language understanding](https://arxiv.org/abs/1810.04805) (2018): One of the first publicly available LLMs, with many variants still in use today. ([blog post](https://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html))
- [Improving language understanding by generative pre-training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) (2018): The first paper from OpenAI covering the GPT architecture, which has become the dominant development path in LLMs. ([blog post](https://openai.com/research/language-unsupervised))
- [Language models are few-shot learners](https://arxiv.org/abs/2005.14165) (2020): The OpenAI paper that describes GPT-3 and the decoder-only architecture of modern LLMs.
- [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155) (2022): OpenAI’s paper explaining InstructGPT, which utilizes humans in the loop to train models and, thus, better follow the instructions in prompts. This was one of the key unlocks that made LLMs accessible to consumers (e.g., via ChatGPT). ([blog post](https://openai.com/research/instruction-following))
- [LaMDA: language models for dialog applications](https://arxiv.org/abs/2201.08239) (2022): A model form Google specifically designed for free-flowing dialog between a human and chatbot across a wide variety of topics. ([blog post](https://blog.google/technology/ai/lamda/)) 
- [PaLM: Scaling language modeling with pathways](https://arxiv.org/abs/2204.02311) (2022): PaLM, from Google, utilized a new system for training LLMs across thousands of chips and demonstrated larger-than-expected improvements for certain tasks as model size scaled up. ([blog post](https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html)). See also the [PaLM-2 technical report](https://arxiv.org/abs/2305.10403).
- [OPT: Open Pre-trained Transformer language models](https://arxiv.org/abs/2205.01068) (2022): OPT is one of the top performing fully open source LLMs. The release for this 175-billion-parameter model comes with code and was trained on publicly available datasets. ([blog post](https://ai.facebook.com/blog/democratizing-access-to-large-scale-language-models-with-opt-175b/))
- [Training compute-optimal large language models](https://arxiv.org/abs/2203.15556) (2022): The Chinchilla paper. It makes the case that most models are data limited, not compute limited, and changed the consensus on LLM scaling. ([blog post](https://www.deepmind.com/blog/an-empirical-analysis-of-compute-optimal-large-language-model-training))
- [GPT-4 technical report](https://arxiv.org/abs/2303.08774) (2023): The latest and greatest paper from OpenAI, known mostly for how little it reveals! ([blog post](https://openai.com/research/gpt-4)). The [GPT-4 system card](https://cdn.openai.com/papers/gpt-4-system-card.pdf) sheds some light on how OpenAI treats hallucinations, privacy, security, and other issues.
- [LLaMA: Open and efficient foundation language models](https://arxiv.org/abs/2302.13971) (2023): The model from Meta that (almost) started an open-source LLM revolution. Competitive with many of the best closed-source models but only opened up to researchers on a restricted license. ([blog post](https://ai.facebook.com/blog/large-language-model-llama-meta-ai/))
- [Alpaca: A strong, replicable instruction-following model](https://crfm.stanford.edu/2023/03/13/alpaca.html) (2023): Out of Stanford, this model demonstrates the power of instruction tuning, especially in smaller open-source models, compared to pure scale.

 注意力就是你需要的（2017）：Google Brain 开始这一切的工作和研究论文。 （博客文章） BERT：用于语言理解的深度双向变压器预训练（2018年）：第一个公开可用的 LLM，至今仍在使用许多变体。（博客文章）通过生成式预训练提高语言理解能力（2018年）：OpenAI 的第一篇关于 GPT 架构的文章，已成为当今 LLM 发展的主要路径。 （博客文章）语言模型是少量样本学习者（2020年）：描述 GPT-3 和现代 LLM 中解码器架构的 OpenAI 文章。 使用人类反馈来训练语言模型以遵循指令（2022年）：OpenAI 关于 InstructGPT 的文章，利用了人类在环中来训练模型，并因此更好地遵循提示中的指令。 这是使 LLM 对消费者（例如通过 ChatGPT）变得可访问的关键解锁之一。（博客文章） LaMDA：对话应用程序的语言模型（2022年）：一种由谷歌专门设计的模型，在各种主题之间进行自由流畅的人机对话。 （博客文章） PaLM：通过途径扩展语言建模（2022年）：PaLM 是来自谷歌的一种新系统，用于跨数千个芯片对 LLM 进行培训，并且随着模型大小的增加，某些任务的表现超出了预期。 （博客文章）。 另见 PaLM-2 技术报告。 OPT：开放预训练转换器语言模型（2022年）：OPT 是表现最好的完全开源 LLM 之一。 此 175 亿参数模型的发布附带代码并基于公共数据集进行了训练。 （博客文章） 训练计算最优的大规模语言模型（2022年）：Chinchilla 研究。 它表明大多数模型都是数据受限而非计算受限，并改变了 LLM 规模共识。 （博客文章） GPT-4 技术报告（2023年）：OpenAI 最新的、最伟大的文章，因其揭示得很少而闻名！ （博客文章）。 GPT-4 系统卡展示了 OpenAI 如何处理幻觉、隐私、安全和其他问题。 LLaMA：开放和高效的基线语言模型（2023年）：Meta 的模型几乎引发了开源 LLM 革命。 其性能与许多最佳闭源模型竞争，但仅向研究人员开放受限制的许可证。 （博客文章） Alpaca：强大的、可重复的指令遵循模型（2023年）：斯坦福大学的研究人员开发了一个模型，证明了相对于纯规模而言，指令微调在较小的开源模型中的力量。  
###  模型改进（例如微调、检索和注意力） 

- [Deep reinforcement learning from human preferences](https://proceedings.neurips.cc/paper_files/paper/2017/file/d5e2c0adad503c91f91df240d0cd4e49-Paper.pdf) (2017): Research on reinforcement learning in gaming and robotics contexts, that turned out to be a fantastic tool for LLMs.
- [Retrieval-augmented generation for knowledge-intensive NLP tasks](https://arxiv.org/abs/2005.11401) (2020): Developed by Facebook, RAG is one of the two main research paths for improving LLM accuracy via information retrieval. ([blog post](https://ai.facebook.com/blog/retrieval-augmented-generation-streamlining-the-creation-of-intelligent-natural-language-processing-models/))
- [Improving language models by retrieving from trillions of tokens](https://arxiv.org/abs/2112.04426) (2021): RETRO, for “Retrieval Enhanced TRansfOrmers,” is another approach—this one by DeepMind—to improve LLM accuracy by accessing information not included in their training data. ([blog post](https://www.deepmind.com/blog/improving-language-models-by-retrieving-from-trillions-of-tokens))
- [LoRA: Low-rank adaptation of large language models](https://arxiv.org/abs/2106.09685) (2021): This research out of Microsoft introduced a more efficient alternative to fine-tuning for training LLMs on new data. It’s now become a standard for community fine-tuning, especially for image models.
- [Constitutional AI (2022)](https://arxiv.org/abs/2212.08073): The Anthropic team introduces the concept of reinforcement learning from AI Feedback (RLAIF). The main idea is that we can develop a harmless AI assistant with the supervision of other AIs.
- [FlashAttention: Fast and memory-efficient exact attention with IO-awareness](https://arxiv.org/abs/2205.14135) (2022): This research out of Stanford opened the door for state-of-the-art models to understand longer sequences of text (and higher-resolution images) without exorbitant training times and costs. ([blog post](https://ai.stanford.edu/blog/longer-sequences-next-leap-ai/))
- [Hungry hungry hippos: Towards language modeling with state space models](https://arxiv.org/abs/2212.14052) (2022): Again from Stanford, this paper describes one of the leading alternatives to attention in language modeling. This is a promising path to better scaling and training efficiency. ([blog post](https://hazyresearch.stanford.edu/blog/2023-01-20-h3))

 从人类偏好中进行深度强化学习（2017年）：研究在游戏和机器人技术背景下进行的强化学习，这成为LLMs的一个出色工具。知识密集型NLP任务的检索增强生成（2020年）：由Facebook开发的RAG是通过信息检索提高LLM准确性的两个主要研究路径之一。（博客文章）通过检索万亿个令牌来改进语言模型（2021年）：RETRO，“ Retrieval Enhanced TRansfOrmers”，是DeepMind提出的另一种方法——这种方法可以访问不包含在训练数据中的信息，以提高LLM的准确性。（博客文章）LoRA：大型语言模型的低秩适应性（2021年）：微软的研究介绍了一种比微调更高效的训练新数据的方法。它已成为社区微调的标准，尤其是图像模型。宪法AI（2022年）：Anthropic团队提出了人工智能反馈强化学习的概念（RLAIF）。主要想法是我们可以通过其他人工智能的监督来开发一个无害的人工智能助手。FlashAttention：快速且内存高效的精确注意力与IO意识（2022年）：斯坦福大学的研究为最先进的模型打开了理解较长文本序列（以及更高分辨率图像）的大门，而无需过度的培训时间和成本。（博客文章）饥饿的饥饿河马：向状态空间模型的语言建模迈进（2022年）：再次来自斯坦福大学，这篇论文描述了语言建模的一种领先替代方案。这是提高规模和训练效率的一个有前途的方向。（博客文章）  
### 图像生成模型  

- [Learning transferable visual models from natural language supervision](https://arxiv.org/abs/2103.00020) (2021): Paper that introduces a base model—CLIP—that links textual descriptions to images. One of the first effective, large-scale uses of foundation models in computer vision. ([blog post](https://openai.com/research/clip))
- [Zero-shot text-to-image generation](https://arxiv.org/abs/2102.12092) (2021): This is the paper that introduced DALL-E, a model that combines the aforementioned CLIP and GPT-3 to automatically generate images based on text prompts. Its successor, DALL-E 2, would kick off the image-based generative AI boom in 2022. ([blog post](https://openai.com/research/dall-e))
- [High-resolution image synthesis with latent diffusion models](https://arxiv.org/abs/2112.10752) (2021): The paper that described Stable Diffusion (after the launch and explosive open source growth).
- [Photorealistic text-to-image diffusion models with deep language understanding](https://arxiv.org/abs/2205.11487) (2022): Imagen was Google’s foray into AI image generation. More than a year after its announcement, the model has yet to be released publicly as of the publish date of this piece. ([website](https://imagen.research.google/))
- [DreamBooth: Fine tuning text-to-image diffusion models for subject-driven generation](https://arxiv.org/abs/2208.12242) (2022): DreamBooth is a system, developed at Google, for training models to recognize user-submitted subjects and apply them to the context of a prompt (e.g. [USER] smiling at the Eiffel Tower). ([website](https://dreambooth.github.io/))
- [Adding conditional control to text-to-image diffusion models](https://arxiv.org/abs/2302.05543) (2023): This paper from Stanford introduces ControlNet, a now very popular tool for exercising fine-grained control over image generation with latent diffusion models.
- 
从自然语言监督中学习可迁移的视觉模型（2021）：介绍了一个基线模型——CLIP，它将文本描述与图像联系起来。这是计算机视觉领域第一个有效且大规模使用基础模型的例子。（博客文章）零样本文本到图像生成（2021）：这篇论文介绍了DALL-E，一个结合了上述CLIP和GPT-3的模型，可以根据文本提示自动生成图像。它的继任者，DALL-E 2，在2022年启动了基于图像的生成AI热潮。（博客文章）利用潜在扩散模型进行高分辨率图像合成（2021）：描述了Stable Diffusion（在发布后爆炸式开源增长之后）。具有深度语言理解的文本到图像扩散模型（2022）：Imagen是谷歌进入人工智能图像生成领域的尝试。在本篇文章发表时，该模型尚未公开发布。（网站）DreamBooth：为以用户为中心的生成训练文本到图像扩散模型（2022）：DreamBooth是一个由谷歌开发的系统，用于训练模型识别用户提交的主题，并将其应用于提示上下文（例如[用户]微笑面对埃菲尔铁塔）。 （网站）添加条件控制到文本到图像扩散模型（2023）：斯坦福大学的一篇论文引入了ControlNet，这是一个非常流行的工具，可以对潜在扩散模型的图像生成进行精细控制。  
###  代理商 

- [A path towards autonomous machine intelligence](https://openreview.net/pdf?id=BZ5a1r-kVsf) (2022): A proposal from Meta AI lead and NYU professor Yann LeCun on how to build autonomous and intelligent agents that truly understand the world around them.
- [ReAct: Synergizing reasoning and acting in language models](https://arxiv.org/abs/2210.03629) (2022): A project out of Princeton and Google to test and improve the reasoning and planning abilities of LLMs. ([blog post](https://ai.googleblog.com/2022/11/react-synergizing-reasoning-and-acting.html))
- [Generative agents: Interactive simulacra of human behavior](https://arxiv.org/abs/2304.03442) (2023): Researchers at Stanford and Google used LLMs to power agents, in a setting akin to “The Sims,” whose interactions are emergent rather than programmed.
- [Reflexion: an autonomous agent with dynamic memory and self-reflection](https://arxiv.org/abs/2303.11366) (2023): Work from researchers at Northeastern University and MIT on teaching LLMs to solve problems more reliably by learning from their mistakes and past experiences.
- [Toolformer: Language models can teach themselves to use tools](https://arxiv.org/abs/2302.04761) (2023): This project from Meta trained LLMs to use external tools (APIs, in this case, pointing to things like search engines and calculators) in order to improve accuracy without increasing model size. 
- [Auto-GPT: An autonomous GPT-4 experiment](https://github.com/Significant-Gravitas/Auto-GPT): An open source experiment to expand on the capabilities of GPT-4 by giving it a collection of tools (internet access, file storage, etc.) and choosing which ones to use in order to solve a specific task.
- [BabyAGI](https://github.com/yoheinakajima/babyagi): This Python script utilizes GPT-4 and vector databases (to store context) in order to plan and executes a series of tasks that solve a broader objective.

 通往自主机器智能的道路（2022）：Meta AI 领导和纽约大学教授 Yann LeCun 提出的如何构建真正理解周围世界的自主智能代理。ReAct：语言模型中的推理与行动协同 （2022）：普林斯顿大学和谷歌的一项项目，旨在测试并改进 LLM 的推理和规划能力。（博客文章）生成型代理：人类行为的交互式仿真体（2023）：斯坦福大学和谷歌的研究人员使用 LLM 来驱动代理，在类似于“模拟人生”的环境中，其互动是自发而非编程的结果。Reflexion：具有动态记忆和自我反思的自主代理（2023）：来自东北大学和麻省理工学院的研究人员的工作，通过学习从错误中吸取教训以及过去的经验来教 LLM 更可靠地解决问题。Toolformer：语言模型可以自己学会使用工具（2023）：该项目训练了 LLM 使用外部工具（例如 API，本例中指向搜索引擎和计算器等），以提高准确性而无需增加模型大小。 Auto-GPT：一个自主的 GPT-4 实验：这是一个开源实验，旨在扩展 GPT-4 的能力，为其提供一系列工具（互联网访问、文件存储等），并选择其中哪些工具用于解决特定任务。BabyAGI：这个 Python 脚本利用 GPT-4 和矢量数据库（用于存储上下文）来计划和执行一系列任务，以实现更广泛的目标。  
### 其他数据模态  
### 代码生成  

- [Evaluating large language models trained on code](https://arxiv.org/abs/2107.03374) (2021): This is OpenAI’s research paper for Codex, the code-generation model behind the GitHub Copilot product. ([blog post](https://openai.com/blog/openai-codex))
- [Competition-level code generation with AlphaCode](https://www.science.org/stoken/author-tokens/ST-905/full) (2021): This research from DeepMind demonstrates a model capable of writing better code than human programmers. ([blog post](https://www.deepmind.com/blog/competitive-programming-with-alphacode))
- [CodeGen: An open large language model for code with multi-turn program synthesis](https://arxiv.org/abs/2203.13474) (2022): CodeGen comes out of the AI research arm at Salesforce, and currently underpins the Replit Ghostwriter product for code generation. ([blog post](https://blog.salesforceairesearch.com/codegen/))
- 
 评估基于代码训练的大语言模型（2021）：这是OpenAI关于Codex的研究论文，Codex是GitHub Copilot产品的代码生成模型。（博客文章）AlphaCode的竞赛级代码生成（2021）：DeepMind的研究展示了比人类程序员编写更好的代码的模型。 （博客文章）CodeGen：一个开源的大语言模型，用于多轮程序合成的代码（2022）：CodeGen来自Salesforce的人工智能研究部门，并且目前支撑着Replit Ghostwriter产品中的代码生成。 （博客文章）  
### 视频生成  

- [Make-A-Video: Text-to-video generation without text-video data](https://arxiv.org/abs/2209.14792) (2022): A model from Meta that creates short videos from text prompts, but also adds motion to static photo inputs or creates variations of existing videos. ([blog post](https://makeavideo.studio/))
- [Imagen Video: High definition video generation with diffusion models](https://arxiv.org/abs/2210.02303) (2022): Just what it sounds like: a version of Google’s image-based Imagen model optimized for producing short videos from text prompts. ([website](https://imagen.research.google/video/))
- 
Make-A-Video：文本到视频生成（无文本视频数据）(2022)：Meta开发的模型，从文本提示中创建短片，但也可以为静态照片输入添加运动或创建现有视频的变体。（博客文章）Imagen Video：使用扩散模型进行高清视频生成（2022年）：正如其名称所暗示的那样：Google图像基础的Imagen模型的一个版本，专门用于从文本提示中产生短片。 （网站）  
### 人类生物学和医学数据  

- [Strategies for pre-training graph neural networks](https://arxiv.org/pdf/1905.12265.pdf) (2020): This publication laid the groundwork for effective pre-training methods useful for applications across drug discovery, such as molecular property prediction and protein function prediction. ([blog post](https://snap.stanford.edu/gnn-pretrain/))
- [Improved protein structure prediction using potentials from deep learning](https://www.nature.com/articles/s41586-019-1923-7) (2020): DeepMind’s protein-centric transformer model, AlphaFold, made it possible to predict protein structure from sequence—a true breakthrough which has already had far-reaching implications for understanding biological processes and developing new treatments for diseases. ([blog post](https://www.deepmind.com/blog/alphafold-a-solution-to-a-50-year-old-grand-challenge-in-biology)) ([explainer](https://www.blopig.com/blog/2021/07/alphafold-2-is-here-whats-behind-the-structure-prediction-miracle/))
- [Large language models encode clinical knowledge](https://arxiv.org/abs/2212.13138) (2022): Med-PaLM is a LLM capable of correctly answering US Medical License Exam style questions. The team has since published results on the performance of Med-PaLM2, which achieved a score on par with “expert” test takers. Other teams have performed similar experiments with [ChatGPT](https://www.medrxiv.org/content/10.1101/2022.12.19.22283643v2) and [GPT-4](https://arxiv.org/abs/2303.13375). ([video](https://www.youtube.com/watch?v=saWEFDRuNJc))
- 
预训练图神经网络策略（2020）：该出版物为有效预训练方法奠定了基础，这些方法适用于药物发现等应用中的分子性质预测和蛋白质功能预测。 （博客文章）使用深度学习潜力的蛋白质结构预测改进（2020年）：DeepMind的以蛋白质为中心的Transformer模型AlphaFold使从序列中预测蛋白质结构成为可能——这是一个真正的突破，已经对理解生物过程和发展新疗法产生了深远的影响。（博客文章）（解释者）大型语言模型编码临床知识（2022年）：Med-PaLM是一种能够正确回答美国医学执照考试风格问题的大规模语言模型。团队随后发布了Med-PaLM 2的表现结果，其得分与“专家”测试者相当。其他团队也进行了类似的实验，使用ChatGPT和GPT-4。 （视频）  
### 音频生成  

- [Jukebox: A generative model for music](https://arxiv.org/abs/2005.00341) (2020): OpenAI 使用 Transformer 进行音乐生成，能够最小化训练生产音乐、人声和歌词。 ([blog post](https://openai.com/research/jukebox))
- [AudioLM: a language modeling approach to audio generation](https://arxiv.org/pdf/2209.03143.pdf) (2022): AudioLM是谷歌的一个项目，用于生成多种类型的音频，包括语音和乐器。 ([blog post](https://ai.googleblog.com/2022/10/audiolm-language-modeling-approach-to.html))
- [MusicLM: Generating nusic from text](https://arxiv.org/abs/2301.11325) (2023): 当前人工智能音乐生成的前沿技术，显示了比以前尝试更高的质量和连贯性。 ([blog post](https://google-research.github.io/seanet/musiclm/examples/))

### 多维图像生成

- [NeRF: Representing scenes as neural radiance fields for view synthesis](https://arxiv.org/abs/2003.08934) (2020): 来自加州大学伯克利分校领导的团队关于“使用五维坐标生成复杂场景的新视图”的研究。([website](https://www.matthewtancik.com/nerf))
- [DreamFusion: Text-to-3D using 2D diffusion](https://arxiv.org/pdf/2209.14988.pdf) (2022): 谷歌和加州大学伯克利分校的研究人员在NeRF的基础上构建了从二维输入生成三维图像的工作。 ([website](https://dreamfusion3d.github.io/))



