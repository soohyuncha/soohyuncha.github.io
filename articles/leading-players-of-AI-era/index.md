---
layout: post
title: "A Top-Down Perspective on the AI Industry: From Applications to Silicon"
date: 2026-05-23
article: true
---

AI has become an integral part of our daily lives. We now consult ChatGPT or Gemini instead of traditional search engines, and Claude Code generates hundreds of lines of code from simple natural language commands --- the media has dubbed "vibe coding".

This article focuses on **LLM-based applications**, the primary catalysts of the current AI revolution. Meanwhile, their massive requirements for computation, memory bandwidth, and storage introduce significant system-level challenges across a wide range of fields, shaping the broad AI industry. (For clarity, I will use the term "AI" to refer specifically to LLMs.)

The global AI ecosystem comprises diverse companies, and in this article, I classify key participants through a ***vertical lens***, spanning **from high-level applications to silicon fabrication**. To visualize this flow, imagine a user prompt entering Gemini: it passes through a software stack, lands in a data center, maps to a specific processor, and finally resolves into circuit-level computations.

The goal of this article is to provide a comprehensive and structured overview of the AI industry and the key technologies that define each industry leader. Even if you are not an engineer in the AI field, you can build your own insights into how the AI industry evolves, which might bring some new opportunities --- perhaps for your investment portfolio 😉📈.

The diagram below captures the big picture of **leading players of the AI ecosystem**, classified into 7 layers from AI applications to silicon fabrication. 

<p>
  <a href="#layer-1">Layer 1: AI Applications</a> <br>
  <a href="#layer-2">Layer 2: Foundation Models</a> <br>
  <a href="#layer-3">Layer 3: Software Frameworks</a> <br>
  <a href="#layer-4">Layer 4: Cloud Infrastructures</a> <br>
  <a href="#layer-5">Layer 5: Processors</a> <br>
  <a href="#layer-6">Layer 6: High-Speed Memory and Interconnect</a> <br>
  <a href="#layer-7">Layer 7: Silicon Fabrication</a> <br>
</p>

<img class="post-img post-img-full-mobile" style="width: 80%; max-width: 900px;" src="{{ page.dir | append: 'image/big_picture/big-picture.png' | relative_url }}" alt="Big picture"/>

<br>

<!-- Layer 1-->
<!--
 - 1st paragraph: What is the role of this layer?
 - 2nd paragraph: Who is the leading player and what is its most famous product?
 - 3rd paragraph: What is the key competitiveness in this layer? 
-->
<div class="post-subtitle" id="layer-1">
Layer 1: AI Applications - Frontline of Human-AI Interaction
</div>
AI applications directly interact with users, providing specific functionalities for our daily lives. The most representative examples are **conversational AI services**, such as Claude (Anthropic), Gemini (Google), Copilot (Microsoft), ChatGPT (OpenAI), and Perplexity (Perplexity AI) [^alphabetical].

Another powerful example is **software development**. While conversational AI services can generate code snippets from natural language prompts, specialized tools like Claude Code (Anthropic), Cursor (Anysphere), and GitHub Copilot (GitHub and OpenAI) provide advanced features such as perceiving the working directory, real-time autocompletion, executing and testing generated code directly in the user's environment. This article is also drafted in Cursor and revised using Claude and Gemini 🫠.

Core competitiveness in this layer lies in understanding **which tasks people wish to delegate to machines**, and translating those tasks into an **optimal combination of AI model APIs and proper tools** based on a deep understanding of each model's unique capabilities.

<br>

<div class="post-subtitle" id="layer-2">
Layer 2: Foundation Models - Source of Generative Capabilities
</div>
At the core of AI applications lies the iterative invocation of **generative foundation models** --- models **pre-trained to predict the most probable next token** from a vast vocabulary based on the given prompt. The newly generated token is appended to the existing sequence --- starting with the user's prompt --- to predict the subsequent one, continuing until the response is completed.

Representative models include Qwen (Alibaba), DeepSeek (DeepSeek), EXAONE (LG AI Research), Llama (Meta), Phi (Microsoft), and Mistral (Mistral AI), which are distributed as ***open-weights***; and finally Claude (Anthropic), Gemini (Google), and GPT (OpenAI), which remain ***closed-source***. Their generative capabilities are evaluated through benchmarks across diverse domains, such as question answering, code completion, or mathematical reasoning.

Core competitiveness in this layer lies in constructing high-quality **training datasets**, designing training recipes, **aligning models with human preferences** and AI safety standards, and optimizing **model architectures** (e.g., Grouped Query Attention, Mixture-of-Experts).

<br>


<div class="post-subtitle" id="layer-3">
Layer 3: Software Frameworks - Open Source APIs to Execute Models
</div>
Generative AI models share a standardized sequential execution flow --- token by token --- and core computational patterns, such as large-scale matrix multiplication, or nonlinear operations (e.g., softmax, GELU). To abstract away the implementation details of these operations, **open-source software frameworks** have emerged, providing an **intuitive, high-level programming interface for model development**.

**Hugging Face** serves as the central model hub, hosting pre-trained weights. **PyTorch** is a tensor-based programming framework that maps tensor operations to diverse processors (e.g., NVIDIA GPU, Google TPU). **vLLM** is a high-throughput serving framework that handles concurrent requests and manages the key-value cache --- a critical memory component in LLM serving. **Triton** is a specialized compiler for writing hardware-aware parallel kernels directly in Python.

Core competitiveness in this layer is profiling the execution patterns when serving models, **diagnosing computational and memory bottleneck**, and wrapping these complexities into **intuitive APIs** that machine learning programmers can easily invoke, while **ensuring optimized performance** on major hardware processors.

<br>


<div class="post-subtitle" id="layer-4">
Layer 4: Cloud Infrastructures - Platform for Resource Allocation
</div>
Requests from AI applications ultimately land on physical hardware in data centers. Since cloud providers support a wide range of services simultaneously, their core mission is **resource allocation** to maximize utilization in response to fluctuating request patterns. This is achieved through a virtualization layer that transforms the physical resources --- CPUs, memory, and GPUs --- into flexible, software-managed units.

Major cloud services include AWS (Amazon), Google Cloud (Google), Microsoft Azure (Microsoft), and Oracle Cloud (Oracle). They offer specific **SLA** (Service Level Agreement) --- latency and throughput --- to ensure reliable performance for application service players.

Core competitiveness in this layer is to provide a **virtualization layer** that enables hosting numerous applications concurrently while ensuring service quality, and massive-scale **interconnectivity** that integrates many processors into a unified computing source --- and of course, a *deep enough bank account* 😲 to build an **enormous high-performance computing infrastructure**.

<br>


<div class="post-subtitle" id="layer-5">
Layer 5: Processors - Specialized Hardware for Parallel Computations
</div>
AI models require massive computation, with ***parallelism*** at its core. This has driven the emergence of **specialized parallel processors**, going beyond the traditional CPU, which is inherently designed as a sequential processor. These specialized chips consist of numerous homogeneous processing elements that efficiently execute simple operations. *Dedicated software library or compilers* are tightly integrated with hardware to maximize utilization of its resource.

**NVIDIA GPUs** dominate the data center market, powered by ***CUDA***, a low-level programming environment for flexible design of parallel computation flows. **Google's TPU** employs a *systolic array*, a specialized architecture for matrix multiplication dataflow. **AMD's GPU** is another alternative with its software stack *ROCm*, which is a similar concept to CUDA. Amazon, Apple, Meta, and Microsoft are also building custom AI processors, with Broadcom and Marvell Technology involved in silicon-level design. **NPU startups** such as Cerebras, FuriosaAI, Groq, Rebellions, SambaNova, and Tenstorrent target the AI inference market with their own optimized hardware.

Core competitiveness in this layer is to design specialized hardware that is simpler than general processors (CPU, GPU), but optimized for key computation and data movement patterns. Building a **software stack** --- ranging from low-level machine code to high-level AI frameworks --- is also crucial, enabling engineers and developers across layers 1 to 4 to fully leverage the capabilities of the new hardware.

<br>


<div class="post-subtitle" id="layer-6">
Layer 6: High-Speed Memory and Interconnect
</div>
Performance of specialized processors (layer 5) depends not only on chip design itself, but also on high-speed data access and chip-to-chip communication. The two key components that are tightly coupled with the processors are **memory** and **interconnect**.

First, as LLM applications require increasingly high memory bandwidth and capacity, **HBM** (High-Bandwidth Memory) has emerged as the key technology for GPU VRAM. Unlike conventional GDDR --- using a planar die layout --- HBM *stacks memory dies vertically using TSV* (Through Silicon Via), enabling compact placement directly alongside the processor (e.g., GPU), which widens the memory bus for higher bandwidth. Micron, Samsung Electronics, and SK hynix are the three major players in this space.

Second, since large models exceed the memory capacity of a single chip and require coordinated computation across many processors, **chip-to-chip interconnect** has become critical for system performance. NVIDIA's *NVLink* enables direct GPU-to-GPU data transfer within and across server nodes without CPU intervention. At data center scale, switch chips manage packet-level routing across a server network, with Broadcom being the dominant player in this space.

<br>


<div class="post-subtitle" id="layer-7">
Layer 7: Silicon Fabrication - Physical Realization of Hardware Designs
</div>
All hardware components discussed in the layers above --- processors, memory, and interconnects --- are **physically realized** on a silicon wafer. **CMOS technology**, which leverages the analog current-voltage characteristics of MOSFETs --- electronic devices --- to realize digital operations, lies at the heart of the modern silicon fabrication process. This fabrication service is offered by companies called **foundries**. **TSMC** dominates this market, with Intel and Samsung Electronics as notable competitors.

<br>


<div class="post-subtitle">
So... What is the Takeaway of This Article?
</div>
<!--
  1) Seven layers are not independent, but tightly related!
  2) Engineers should major in at least one layer, but overview could bring a new opportunity
-->
We've walked through the AI industry across seven layers via the vertical lens. One might assume they operate independently, but in practice, they are *deeply interconnected*, with adjacent layers influencing each other most directly.

For example, FlashAttention implements the attention operation --- the core computation pattern of LLMs (layer 2) --- as a hardware-optimized kernel (layer 3), tailored to the compute units and memory hierarchy of specific hardware, NVIDIA GPUs (layer 5). Conversely, sparse attention in DeepSeek is an example of *upward* direction where the hardware constraints (layer 5), such as memory bandwidth, influence the model architecture design (layer 2).

Beyond adjacent layers, innovations can ripple further. For example, higher memory bandwidth delivered by HBM (layer 6) enables data centers (layer 4) to support increasingly memory-intensive workloads --- such as agentic applications at layer 1 maintaining longer user context.

In my opinion, research engineers should have deep expertise in at least one layer, but also keep up with the recent trends and research directions in adjacent layers. This cross-layer awareness can open up new research directions in your target layer. Furthermore, not necessarily frequently, but sometimes --- such as the 10 minutes you just spent on this article 🤓 --- viewing the industry from a wider lens might offer perspectives that are easy to miss when focused deeply on your own layer.

[^alphabetical]: Throughout this article, when multiple companies or products are listed in parallel, they are ordered alphabetically by their official names.

<!--
<div class="post-subtitle">
Acknowledgement
</div>
Who?

<br>
-->

