---
layout: post
title:  "Finetuning Distilbert in Colab and Sagemaker"
date:   2023-05-16 04:59:47 -0400
categories: nlp gpt bias
---

In [this notebook](https://colab.research.google.com/drive/1nCw8RXpyNzKHMkNCfdgPVMwYe2IYLqf2?usp=sharing){:target="_blank"} I fine-tuned distilbert to perform a classification task.  The model was finetuned to distinguish between descriptive and analytic writing.  I gathered data from two human annotators to produce the finetuning dataset.  I perform hyper paratmer tuning on several combinations of hyper parameters.


