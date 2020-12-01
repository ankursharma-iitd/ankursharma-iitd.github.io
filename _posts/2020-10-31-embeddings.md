---
title: "Understanding the political dialogue on Twitter"
date: 2020-10-31
tags: [machine learning, graphs, social, data, media]
excerpt: "Machine Learning, Graphs, Social, Data, Media"
header:
  image: "/images/twitter-politics.png"
mathjax: "true"
---

## Abstract
Understanding political discourse is a challenging research problem since it's hard to tag and identify which politicians are talking about which topics. In this paper, we propose to use representation learning as a window into the political dialogue on social media through the tweets authored by politicians on Twitter. Our primary question in this paper is to understand whether political affiliation is the sole driver of what a politician writes on social media. To this end, we employ representation learning to embed politicians based on their tweets to model which politicians' author similar content, and also propose a novel embedding method to improve some of the shortcomings of the existing methods. The learnt politician embeddings further demonstrate that for both the USA and India, political affiliation is not the only primary driver of what politicians write on Twitter but it is also influenced by their geography. Through our research, we want to highlight that information retrieval methods, such as representation learning, can be used in examining important social and political issues.

---

## Proposed Method

The learning setting of the proposed model is such that given a politician and a tweet they have written, predict `K' sequence words from the tweet with the politician ID as input. Intuitively, the model tries to learn the consistency of the words written by the politician in a tweet, based on their own past tweets -- ergo, _does this sound like they wrote it_. This has obvious challenges, since we don't know if politicians write their own tweets, or if those who write their tweets are necessarily consistent.

However, the assumption we go with is that  politicians who talk about similar topics should have similar embeddings. This is generally true since similar word distributions are used for similar topics, and if multiple politicians are talking about the same topics, the model will output words from the same distribution.  Thus, the function that the model tries to approximate is $$\Phi(P_{i}, w_{j}) = \{0, 1\}$$
where #$P_{i}$# is the unique ID of the politician, $$w_{j}$$ is a word and the label $$\{0, 1\}$$ is decided whether that word $$w_{j}$$ occurred in the sampled `K' words of the tweets that the politician has authored.

![alt]({{ site.url }}{{ site.baseurl }}/images/embedding/1.png)

To approximate $$\Phi$$ from the given data, we propose to use a shallow neural network. Figure 1 shows the outline of the neural network architecture. The input layer corresponds to the politicians and is of the size of the number of politicians. Hidden layer is the size of the embedding dimension that is desired. The output layer is for the output words and is of the size of the vocabulary to enable prediction of words for the input politician. The model is trained to maximize the likelihood of prediction of the `K' words sampled from the tweet. This is stated as follows,

$$
    \mathcal{L}(\theta) = \frac{1}{M}  \frac{1}{K} \sum_{j=1}^{M} \sum_{i=1}^{K} \log( \textit{Pr}(w_{i}, P_{t_{j}}) \mid  \theta)
$$

where $$P_{t_{j}}$$ is the politician who is the author of $$t_{j}^{th}$$ tweet, $$\textit{Pr}$$ is the probability of predicting the word $$w_{i}$$ out of the K words sampled from a tweet written by $$P_{t_{j}}$$, M is the total number of tweets in the dataset and $$\theta$$ denotes the parameters of our model.

## Party Prediction Task
To understand whether what a politician writes is influenced by their political party, we conduct an empirical experiment to predict the party of a politician using the learnt embeddings as features in a logistic regression model. A high accuracy on this task indicates a high degree of correlation (and vice versa) between the content posted by politicians and their respective parties.

We create four types of feature vectors per politician using the tweets for the logistic regression classifier - 1) using TF-IDF ([1]) by constructing TF-IDF weights considering each politician as a document of concatenated tweets written by the respective politician; 2) using Word2Vec ([3]) 3) using User-DBOW model ([4, 5]); and 4) using the proposed method. The experiment using TF-IDF is important to understand if the raw word distributions are sufficient enough to predict the parties of politicians, indicating no need for complex embedding methods. We observe that in the case of the USA, TF-IDF based performs very close to the embedding methods. For the compared embedding methods, we also conduct a hyper-parameter sweep over embedding size (50, 100, 200, 300 and 400) and window size (3,5,8). For evaluation purpose, we measure standard classification metrics - Accuracy, Precision, Recall and F1-score (macro). 

For our experiments, we use the publicly available Nivaduck dataset ([2]) which contains state and party annotations for political screen names for India (13111 politician accounts) and only state tags for the United States of America (4422 political accounts with 1500 accounts with state annotations). We use all accounts for training the embeddings and creating the TF-IDF corpus.

**USA Dataset:** For the USA dataset, since party annotation were not available in the Nivaduck dataset ([2]), we use the tagged dataset of Governors, Senators, and Congress from the Civil Service USA [data](https://github.com/CivilServiceUSA/) as our labelled instances. We further label some more political accounts to go beyond congressional handles, and our total dataset for this experiment is 598 politicians with 319 democrat and 279 republican accounts. We train a logistic regression on the embeddings with labels as the party and do a 15-fold testing of the data. For training each fold, we randomly sample 100 politicians from each party, and remaining politicians act as the test users. 

Table 1 shows the average values of metrics across different folds. It can be seen that TF-IDF gives a 90% accuracy, which is improved slightly by the method proposed in [3]. The User-DBOW approach proposed in [4] improves the results significantly by approximately 5% followed by the proposed method, which is able to predict most accurately and has a gain of more than 1.5% over User-DBOW approach. This shows that the correlation between the word distribution and the party of a politician is significant enough that a TF-IDF feature vector with linear classifier can identify it 90% of the time. Interestingly, our model also predicted _Janet Mills_ (Twitter handle: JanetMillsforME) as a democrat, whereas she was wrongly tagged as a republican in the Civil Services USA dataset. 

### References
1. _Term-weighting approaches in automatic text retrieval - Salton, Gerard and Buckley, Christopher_
2. _PoliTwictionary with NivaDuck - A scalable database of political Twitter handles for India and the United States - Panda, Anmol and Gonawela, Andre and Mishra, Dibyendu and  Mohapatra, Mugdha  Chandrasekaran, Ramgopal and  Pal, Joyojeet, (SM Society, 2020)_
3. _Learning multiview embeddings of twitter users - Benton, Adrian and Arora, Raman and Dredze, Mark (ACL 2016)_
4. _Multi-view unsupervised user feature embedding for social media-based substance use prediction - Ding, Tao and Bickel, Warren K and Pan, Shimei (EMNLP 2017)_
5. _Predicting Delay Discounting from Social Media Likes with Unsupervised Feature Learning - Ding, Tao and Bickel, Warren K and Pan, Shimei (ASONAM 2018)_