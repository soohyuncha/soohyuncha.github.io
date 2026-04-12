---
layout: post
title: "Leading Players of the AI Era: A Top-Down Perspective from Applications to Silicon"
date: 2026-04-15
article: true
---

<!--<div class="post-subtitle">
Understanding Leading Players in AI From Applications to Silicon
</div> -->
AI has become an integral part of our daily lives, transcending its origins in academic theory. We now consult LLM-based chat services like ChatGPT or Gemini instead of traditional search engines. AI generates hundreds of lines of valid code from simple natural language commands—the media has dubbed "vibe coding".

This article focuses specifically on **LLM-based AI applications**, as they are the primary catalysts of the current AI revolution. However, their massive requirements for computation, memory bandwidth, and storage have also created significant bottlenecks in system performance and concerns on power consumption and carbon emission. For clarity, I will use the term "AI" to refer specifically to LLMs unless otherwise noted.

Diverse companies comprise global AI ecosystem, with each player fulfilling a unique role. In this article, I classify these key participants through a ***vertical lens***, spanning **from high-level applications at the top to silicon-level manufacturing at the base**. To visualize this flow, imagine a user prompt entering Gemini: it traverses a data center, maps to a specific processor, and finally resolves into circuit-level computations.

The goal of this article is to provide a comprehensive understanding of the end-to-end flow of AI services and the key technologies that define each industry leader. Research engineers might gain understanding on how their specific layer interacts with the broader stack. Even if you are not an engineer, you can build your own insights into how the AI industry evolves, which might bring some new opportunities—perhaps for your investment portfolio 😉📈.

The diagram below captures the big picture of **leading players of the AI ecosystem**, classified into 7 layers from AI applications to silicon fabrication. 
<!--
Your opening paragraph and any text you want **above** the figure go here. Put `big-picture.png` in `articles/leading-players-of-AI-era/image/`. -->

<img class="post-img" style="width: 80%; max-width: 900px;" src="{{ page.dir | append: 'image/big_picture/big-picture.png' | relative_url }}" alt="Big picture"/>

<br>

<!-- Layer 1-->
<!--
 - 1st paragraph: What is the role of this layer?
 - 2nd paragraph: Who is the leading player and what is its most famous product?
 - 3rd paragraph: What is the key competitiveness in this layer? 
-->
<div class="post-subtitle">
Layer 1: AI Applications - Frontline of Human-AI Interaction
</div>
AI applications directly interact with users, providing specific functionalities for our daily lives. The most representative examples are **conversational AI services**, such as Claude (Anthropic), Gemini (Google), Copilot (Microsoft), ChatGPT (OpenAI), and Perplexity (Perplexity).

Another powerful example is **software development**. While general-purpose conversational AI services can generate code snippets from natural language prompts, specialized tools like Claude Code (Anthropic), Cursor (Anysphere), and GitHub Copilot (GitHub and OpenAI) provide advanced features such as perceiving the working directory, real-time autocompletion, automatically applying AI-generated code to files, and the ability to build and render web applications using AI-generated code. Updates to this blog are typically being drafted in Cursor 🫠.

Core competitiveness in this layer lies in understanding **which tasks people wish to delegate to machines**, and translating those tasks into an **optimal combination of AI model APIs and proper tools** based on a deep understanding of each model's unique capabilities.

<br>

<div class="post-subtitle">
Layer 2: Foundation Models - Source of Generative Capabilities
</div>
AI applications generate responses by iteratively invoking **generative foundation models**, which are **pre-trained to predict the most probable next token from a vast vocabulary** based on the user's prompt. The newly generated token is added to the end of the existing sequence --- which begins with the user's prompt --- to predict the subsequent one, continuing until the response is completed.

Representative models include Qwen (Alibaba), DeepSeek (DeepSeek), Llama (Meta), and EXAONE (LG AI Research), which are distributed as ***open-weights***; Phi (Microsoft) and Mistral (Mistral AI), which provide ***partially open-weights***; and finally Claude (Anthropic), Gemini (Google), and GPT (OpenAI), which remain ***closed-source***. The generative capabilities of these models are evaluated through benchmarks across diverse domains, including question answering, text summarization, code completion, or mathematical reasoning.

Core competitiveness in this layer lies in designing **optimized model architectures** (e.g., computation structures such as Mixture-of-Experts), constructing high-quality **training datasets**, designing training recipes, and **aligning models with human preferences** and AI safety standards.

<br>


<div class="post-subtitle">
Layer 3: Software Frameworks - Open Source APIs to Execute Models
</div>
TODO

<br>


<div class="post-subtitle">
Layer 4: Cloud Infrastructures - Platform for Resource Allocation
</div>
TODO

<br>


<div class="post-subtitle">
Layer 5: Chips - Specialized Hardware for Parallel Computations
</div>
TODO

<br>


<div class="post-subtitle">
Layer 6: Chip Components - High-Speed Memory and Interconnection
</div>
TODO

<br>


<div class="post-subtitle">
Layer 7: Silicon Fabrication - Physical Realization of Chip Designs
</div>
TODO

<br>


<div class="post-subtitle">
Acknowledgement
</div>
Who?

<br>

<!--
More body text can follow the image. Change size by editing the `style` on the same line (for example `max-width: 720px` or `width: 85%`). Use `class="post-img"` for no border; use `class="post-pic"` if you want the thin framed look. -->
