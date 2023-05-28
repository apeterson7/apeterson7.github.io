---
layout: post
title:  "A Novel Bias Mitigation Approach for GPT-2"
date:   2023-05-16 04:59:47 -0400
categories: nlp gpt bias
---

In [this research paper](https://drive.google.com/file/d/16FqZmdpSPP5mBVK16s5Ob9VvSCr--UHZ/view?usp=share_link){:target="_blank"} I applied a new technique to control transformer-based language model output to the task of bias mitigation.

New work by [Geva, et al.](https://arxiv.org/pdf/2203.14680.pdf){:target="_blank} shows that the output of each feed forward network within the transformer blocks of a language model can be understood as an additive update on the token distribution of the model for a given context.  The work also shows that the individual vectors within each FFN can be projected onto the model's output vocabulary to reveal distinct concepts that are often interprettable.  By emphasizing these vectors, the model's behavior can be manipulated. 

With a small group of graduate students, I applied this technique to the task of bias mitigation.  We measured GPT-2 ([Radford, et al.](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf){:target="_blank"}) on three bias benchmarks from Googles [Big Bench project](https://github.com/google/BIG-bench){:target="_blank"} to obtain its baseline performance.  We then experimented with several techniques for selecting FFN value vectors and coefficients with which to emphasize (and de-emphasize) them. We also compare the results with a competing method for bias mitigation: fine-tuning on text from the [StereoSet](https://aclanthology.org/2021.acl-long.416.pdf){:target="_blank"} and compare our results.  

Overall, we observed 58.7% of the bias metrics across the three Big Bench tasks improved using a variation of our method.  Our results show that value vector emphasis may be a promising avenue towards mitigating bias in language models.