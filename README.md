# Classifying arXiv paper using GPT2

Based on my experiments, GPT-2 was unable to perform very well when used for **prompt classification**. This is due to the fact that GPT-2 takes a fixed size input (text equivalent to 1024 tokens) so we cannot fit many examples into the prompt for few shot learning since our dataset classification depends a lot on the abstract text ( as shown in the notebook, classification based on simply title performed very poor). This leads us to believe that GPT-2 and its equivalent transformer models are not very great for text classification when the size of text used for classification is too large.

However, GPT-2 when used as **sequence classifier** performed much better. Because the model takes a lot of context of the input text and presents a good representation of the text, this representation can be used for classification by introducing a fully connected neural network layer to classify and this layer can be trained on just 20 samples which as shown in the notebook, gives much better results based on the precision, recall and f1 score.



**References**

https://arxiv.org/abs/2005.14165 ( Language Models are Few-Shot Learners )

https://huggingface.co/docs/transformers/model_doc/gpt2

https://huggingface.co/docs/transformers/training