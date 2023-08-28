---
layout: post
title:  "Recent Approaches on Accelerating Transformer-based Deep Neural Network"
date:   2023-08-27 00:00:00+0900
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
---


<!-- <img src="{{ "/assets/img/content/post-example/Banner.jpg" | absolute_url }}" alt="bay" class="post-pic"/> -->




### CONTENTS

<span style="font-size: 18px;">
&ensp; &ensp; [1 &nbsp; &nbsp; Introduction](#1-introduction)
<br>
&ensp; &ensp; [2 &nbsp; &nbsp; Background](#2-background)
<br>
&ensp; &ensp; [3 &nbsp; &nbsp; Acceleration Techniques](#3-acceleration-techniques)
<br>
&ensp; &ensp; [4 &nbsp; &nbsp; Discussion](#1-introduction)
<br>
&ensp; &ensp; [5 &nbsp; &nbsp; Conclusion](#1-introduction)
<br>
&ensp; &ensp; [6 &nbsp; &nbsp; Reference](#6-reference)
<br>
</span>


### 1 INTRODUCTION

<span style="font-size: 16px;">
&nbsp; &nbsp; &nbsp; <span style="font-size: 26px;">R</span>ecently, transformer-based deep neural network outperforms in various AI domains such as
NLP (natural language processing), and CV (computer vision). Its key mechanism is <em> attention </em> and it was first introduced in [[1]](#6-reference).
<em> Attention </em> mechanism allows model to attend to tokens differently according to their contextual importance. However, attention mechanism
requires high cost of computation in that its complexity is quadratically proportional to input token length. This limits maximum input sequence length
of model (such as 1024 or 2048), because inference latency and power consumption are important constraints in real world applications using deep neural network.
</span>



<span style="font-size: 16px;">
&nbsp; &nbsp; &nbsp; To address this fundamental limitation, there have been many researches on accelerating transformer especially focused on attention. Two main algorithmic
optimization schemes are <em> quantization </em> and <em> pruning </em>. With these optimization techniques, more hardware efficient implementation is possible.
Compared to execution of inference in general purpose processor such as CPU or GPU, offloading some part of compuation (or maybe full) to dedicated hardware can
achieve high speedup and energy efficiency. It may contribute to more efficient execution of deep neural network applications, and expand limitation of model
capacity such as maximum token length potentially allowing model to do some more complicated and challenging task.
</span>

<span style="font-size: 16px;">
&nbsp; &nbsp; &nbsp; In this article, I will introduce some backgrounds on attention mechanism and mainly analyze two main accelerating technique quantization
and pruning with several recent researches. Finally, I will discuss about this trends and further research topics.
</span>

### 2 BACKGROUND
<img src="{{ "/assets/img/content/transformer/attention_operation.png" | absolute_url }}" alt="attention" >
<br>

<span style="font-size: 16px;">
&nbsp; &nbsp; &nbsp; Transformer-based neural network consists of a stack of transformer layers and additional epilogue layer depending on its target task.
Number of transformer layer varies according to model capacity. For example, BERT-base uses 12 layers whereas BERT-large uses 24 [[2]](#6-reference). 
A single transformer layer is shown in left part of Figure 1.

<span>

### 3 ACCELERATION TECHNIQUES
quantization and pruning

### 6 REFERENCE
<span style="font-size: 16px;">
[1] &nbsp; A. Vaswani. "Attention is all you need." <em> Advances in neural information processing systems 30 </em> (2017).
<br>
[2] &nbsp; J. Devlin. "Bert: Pre-training of deep bidirectional transformers for language understanding." <em> arXiv preprint arXiv:1810.04805 </em> (2018).
</span>


