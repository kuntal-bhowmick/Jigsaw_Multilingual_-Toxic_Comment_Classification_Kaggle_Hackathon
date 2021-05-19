# Jigsaw_Multilingual_-Toxic_Comment_Classification_Kaggle_Hackathon
This is a repository of codes used by me in Kaggle Competition [Jigsaw Multilingual Toxic Comment Classification](https://www.kaggle.com/c/jigsaw-multilingual-toxic-comment-classification)

# Competition Overview :
It only takes one toxic comment to sour an online discussion. The Conversation AI team, a research initiative founded by Jigsaw and Google, builds technology to protect voices in conversation. A main area of focus is machine learning models that can identify toxicity in online conversations, where toxicity is defined as anything rude, disrespectful or otherwise likely to make someone leave a discussion. If these toxic contributions can be identified, we could have a safer, more collaborative internet.

In the previous 2018 Toxic Comment Classification Challenge, Kagglers built multi-headed models to recognize toxicity and several subtypes of toxicity. In 2019, in the Unintended Bias in Toxicity Classification Challenge, you worked to build toxicity models that operate fairly across a diverse range of conversations. This year, we're taking advantage of Kaggle's new TPU support and challenging you to build multilingual models with English-only training data.

Jigsaw's API, Perspective, serves toxicity models and others in a growing set of languages (see our documentation for the full list). Over the past year, the field has seen impressive multilingual capabilities from the latest model innovations, including few- and zero-shot learning. We're excited to learn whether these results "translate" (pun intended!) to toxicity classification. Your training data will be the English data provided for our previous two competitions and your test data will be Wikipedia talk page comments in several different languages.

As our computing resources and modeling capabilities grow, so does our potential to support healthy conversations across the globe. Develop strategies to build effective multilingual models and you'll help Conversation AI and the entire industry realize that potential.

Disclaimer: The dataset for this competition contains text that may be considered profane, vulgar, or offensive.

# My Solution Description :
I have mainly used different variants of BERT and Roberta in this competition. In BERT, I have used DistilBERT,Bert Multilingual,Bert base and Bert large where each of them had around 5 different models based on different Learning Rate,Input text length,Pseudo Labelling etc.

## Preprocessing : 
I have done minimal preprocessing in BERT and Roberta models.

## Loss function : 
I have used Focal Loss as we had imbalanced dataset in this competition.

## Callbacks : WIP 

## Ensemble : 
I have used 2 layer ensembling here. At first layer, I have created weighted average ensembling separately for Bert Base,Bert Large,Distillbert,Bert ML and Roberta.
So , if I have 5 different models of Bert Base based on different LR and Input text length then I took weighted average of those and created one blended BERT base model.Similarly, I had blended models of XLM Roberta,Bert Multilingual,Bert Large and DistilBert as well where each of them are constructed using 4-5 different model variants using weighted average.
Finally in 2nd layer, I took weighted average of all of these blended models. This 2 layer ensembling had given me better results for sure , it helped me to finish very close to Top 5% otherwise with single layer ensemble I would have been around Top 10% only.

## My Performance : 
  Private/Final Rank : 84/1621 (Top 6%)
