# SkimLit
* An NLP model to classify abstract sentences into the role they play.
*This project is the implementation of the research paper: [PubMed 200k RCT: a Dataset for Sequential Sentence Classification in Medical Abstracts](https://arxiv.org/abs/1710.06071).

## Dataset: [PubMed 200k RCT dataset](https://github.com/Franck-Dernoncourt/pubmed-rct#readme)
>> PubMed 200k RCT is a new dataset based on PubMed for sequential sentence classification. The dataset consists of approximately 200,000 abstracts of randomized controlled trials, totaling 2.3 million sentences. Each sentence of each abstract is labeled with its role in the abstract using one of the following classes: background, objective, method, result, or conclusion. The purpose of releasing this dataset is twofold. First, the majority of datasets for sequential short-text classification (i.e., classification of short texts that appear in sequences) are small: we hope that releasing a new large dataset will help develop more accurate algorithms for this task. Second, from an application perspective, researchers need better tools to efficiently skim through the literature. Automatically classifying each sentence in an abstract would help researchers read abstracts more efficiently, especially in fields where abstracts may be long, such as the medical field.

* PubMed 20k is a subset of PubMed 200k. I.e., any abstract present in PubMed 20k is also present in PubMed 200k.
* PubMed_200k_RCT is the same as PubMed_200k_RCT_numbers_replaced_with_at_sign, except that in the latter, all numbers had been replaced by @. (same for PubMed_20k_RCT vs. PubMed_20k_RCT_numbers_replaced_with_at_sign).

## Models Used: A total of 6 models were trained on the whole dataset
![accuracy](https://github.com/garvit088/SkimLit/assets/97309123/8d0ec2b2-c926-40f8-9c99-819bac335274)

* A Multinomial Naive Bayes Classifier with **74.9%** accuracy.
* A Convolution Custom Token Embedding model gave **83.6%** accuracy.
* A Pretrained Token Embedding (Universal Sentence Encoder) model gave **77.6%** accuracy.
* A Convolution Custom Character Embedding model gave **72.7%** accuracy.
* A hybrid model consisting of both Token and Character Embedding gave **77.6%** accuracy.
* A tribrid model consisting of Token, Character, and Position Embedding gave **86.9%** accuracy.
  
![output](https://github.com/garvit088/SkimLit/assets/97309123/f432996b-9011-4f20-98b4-e09d5e97c2b3)

## Skimlit Tribrid Model:
> This particular model consists of three different types of embeddings, namely: Token, Character, and Position Embeddins. For the position embedding, the abstract was disentangled into line numbers (Sequence of the sentence in the abstract) and total lines (Total sentences in the abstract).

![model](https://github.com/garvit088/SkimLit/assets/97309123/6cffe6df-d135-4785-9e66-85e90a77c0a3)

