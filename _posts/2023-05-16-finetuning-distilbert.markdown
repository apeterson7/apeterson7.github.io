---
layout: post
title:  "Finetuning Distilbert in Colab and Sagemaker"
date:   2023-05-16 04:59:47 -0400
categories: nlp gpt bias
---

In [this notebook](https://colab.research.google.com/drive/1nCw8RXpyNzKHMkNCfdgPVMwYe2IYLqf2?usp=sharing){:target="_blank"} I fine-tuned distilbert to perform a classification task:  To distinguish between analytical and descriptive writing in newspaper articles. I gathered data from the New York Times and recruited two human annotators to produce the finetuning dataset.  I performed hyper parameter tuning on several combinations of hyper parameters.  I then tested the model on several adversarial examples. 


