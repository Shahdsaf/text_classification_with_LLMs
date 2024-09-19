# text classification with LLMs

This repo is a case study of text classification with LLMs. It compares the performance on text classification via two methods: 
- Full finetuning of Bert-like LLM models which are relatively small of few hundred millions of parameters.
- Zero-shot text classification via prompt-based in-context learning using super large generative LLMs which are of few dozen/hundred billions of parameters. 

Code is in classification.ipynb and the report and solution are explained in report.pdf

## Data
Using one of the [TweetEval datasets](https://github.com/cardiffnlp/tweeteval/tree/main/datasets), I chose the emotion classification task which includes 3k+ training examples and 10% of that for validation with 4 emotion labels: `anger`, `joy`, `optimism`, `sadness`.

## Models
For full finetuning, I used the [Bert](https://huggingface.co/docs/transformers/en/model_doc/bert) and [Bertweet](https://huggingface.co/docs/transformers/en/model_doc/bertweet) models from Hugging Face. For zero-shot text classification, I used the [Meta LLaMA 3 70B Instruct](https://huggingface.co/meta-llama/Meta-Llama-3-70B-Instruct) model.

## Summary of Results
I was able to reproduce the main results of comparing both methods from literature [[1](https://osf.io/preprints/socarxiv/sthwk), [2](https://arxiv.org/pdf/2403.17661), [3](https://arxiv.org/pdf/2305.16938)]. The main takeaways:
1. In case we have 1000+ data points, we should rely on the full finetuning of relatively small Bert-like models as we can get more robust task-specific SOTA classifiers. 
2. In case we have less data, the results of full finetuning can become less reliable and therefore, we should rely on zero-shot in-context learning. The experiments I did show that zero-shot in-context learning works very well and achieves SOTA results if prompt design and the choice of LLM is done properly.

