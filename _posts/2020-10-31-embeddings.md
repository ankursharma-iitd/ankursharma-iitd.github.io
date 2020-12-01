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

## Party Prediction Task