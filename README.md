# kapa_question_type_classification


## Task 1: creating a classifier of questions 

Since we have enough data (1000+), we can simply do full finetuning of a suitable encoder-only LLM with a randomly initialized classification layer to learn the classification task. We choose an encoder-only transformer-based architecture as they are pretrained using MLM for language modelling and understanding so they excel at extracting information by looking at the entire input at once to create a representation and thus are great at analyzing input data in its entirety in contrast to decoder-based models are trained for generation tasks using CLM methodology for autoregressive generative tasks. 

Zero-shot and few-shots classification have become popular techniques, enabling LLMs to perform classification tasks with no training data or a few examples. However, for better accuracy, it is demonstrated that instruction fine-tuning can improve the performance by tuning LLMs with curated datasets.


### Model 
which model can understand code? and multiple languages?
task is more related to NLP than code-related reasoning
studies showed bert to perform well on code analysis tasks
I tried to use multiple libraries/models like ... to filter out non-english languages but given the scope of this task, I chose to keep the other examples (assuming they are valid) while using an LLM that was train multi-lingual data to 1. increase training data and 2. not lose english examples due to bad filtering


There are different encoder-only models. I will start to experiment with the commonly used one BERT and then if I have time, compare it to other models.

### Experiments

tune hparams
add answer or not?
different models maybe?
 llama and other bert family?
augmentation?
try without adding question/answer prefix
cased?
lower bsize or lr? 
freeze core?
xentropy class balance?
evaluate llama without finetuning 
tune lora of llama
how llama does causal stuff to classify text?