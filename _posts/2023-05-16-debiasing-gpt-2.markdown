---
layout: post
title:  "A Novel Bias Mitigation Approach for GPT-2"
date:   2023-05-16 04:59:47 -0400
categories: nlp gpt bias
---

In [this research paper](https://drive.google.com/file/d/16FqZmdpSPP5mBVK16s5Ob9VvSCr--UHZ/view?usp=share_link){:target="_blank"} I applied a new technique to control transformer-based language model behavior to try to reduce measurable bias in GPT-2.

New research from [Geva, et al.](https://arxiv.org/pdf/2203.14680.pdf){:target="_blank} shows that the output of each feed forward network within the transformer blocks of a language model can be understood as an additive update over the probability distribution of output tokens. The research shows that an FFN update can be viewed as a collection of sub-updates, each corresponding to a weighted value vector in the FFN output. At any layer in the language model, these value vectors can be projected onto the model's output vocabulary. Top scoring tokens in these distributions often correspond to one or more discrete, interprettable concepts (e.g. countries in europe, scientific professions). By emphasizing these vectors, these concepts can be exaggerated, thus manipulating the model's behavior. In the original research, adjusting the coefficients of just 10 value vectors resulted in siginificant decreases in toxicity of completions as scored by the [Perspective API](https://perspectiveapi.com/){:target="_blank}.

With a small group of graduate students, I used an application of this technique to try to reduce bias in GPT-2.  We measured GPT-2 ([Radford, et al.](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf){:target="_blank"}) on three bias benchmarks from Google's [Big Bench project](https://github.com/google/BIG-bench){:target="_blank"} to obtain its baseline performance. Then, we experimented with several techniques for selecting FFN value vectors associated with non-biased concept. Once selected, we emphasized their influence on model output using a range of coefficient values. For comparison, we tried fine-tuning GPT-2 on artifically non-biased text from the [StereoSet](https://aclanthology.org/2021.acl-long.416.pdf){:target="_blank"} dataset to see if we could match or exceed the results produced by our adapted value vector method. 

Overall, we observed 58.7% of the bias metrics across the three Big Bench tasks improved using a variation of our method.  Our results show that value vector emphasis may be a promising avenue towards mitigating bias in language models.

All the code used in the paper can be found in [here](https://github.com/apeterson7/debiasing-ffn-updates){:target="_blank"}.