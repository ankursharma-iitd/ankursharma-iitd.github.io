---
title: "Taxonomy of Indian Politics on Twitter - State-by-State analysis & Connectivity Dynamics"
date: 2020-11-20
tags: [machine learning, graphs, social, data, media]
excerpt: "Machine Learning, Graphs, Social, Data, Media"
header:
  image: "/images/twitter.png"
mathjax: "true"
---

# State-By-State Analysis

This is work dony by Ankur Sharma, Saloni Dash, Himani Negi and Joyojeet Pal at Microsoft Research (MSR) India. Here, we give an example for one of states (Bihar) amongst the set of 20 states that we consider in our main piece.

## Bihar on Social Media
We summarize the key trends with Twitter use among politicians in Bihar.

### Language
We see that for all the parties, tweeting in Hindi gets significantly more retweets than when they tweet in English. The size of the colored bubbles in the scatter plot is proportionate to the share of politicians whose majority tweets (over 50% in any single language) are in either Hindi or English. We see for instance that in all four parties, more politicians use Hindi as their primary language for tweeting than English. We also see that for some parties – RJD and BJP get retweeted much higher when in Hindi than in English.

{% include image.html url="/images/connectivity/1.jpg" description="Figure 1: Twitter activity and retweets of key political parties in Bihar separated by main languages used (2016-2020)" %}

This points to the overall shift towards Hindi language tweeting, however, we do not capture here if there are non-Hindi Devanagiri based languages such as Magahi, Maithili, Bhojpuri etc. One suggestion of these data is that Twitter is increasingly and more effectively (as captured through the rate of retweet) used in local languages.

### Key Players
We gathered all the tweets from the various politicians in Bihar and mapped out the frequency of tweeting, the total retweeting, and the rate to which politicians’ Twitter accounts get retweeted the most. We see in figure 2 that a small number of politicians are very heavily followed and retweeted. Four from among the most followed Bihar politicians online – Lalu Prasad Yadav (RJD), Ravi Shankar Prasad, Giriraj Singh (both BJP), and Shatrugan Sinha (INC) are not candidates in the elections themselves but are either related to candidates and wield significant influence in the social media conversations online by virtue of their presence in the central government.

{% include image.html url="/images/connectivity/2.jpg" description="" %}

We see that while Lalu Yadav remains the titular head of RJD and continues to be both widely followed, Tejashwi Yadav is for all practical purposes the most important leader of the party on social media, both in terms of volume of tweets and extent of retweeting. Lalu’s account is managed on his behalf, and remains an important mechanism of output for the party.

{% include image.html url="/images/connectivity/3.jpg" description="Table 1: Most retweeted politicians, by other Bihar politicians, from the four key parties in the state" %}

Table 1 lists the five most retweeted accounts for each state, by party. We find that the politicians of the state are more prominent in the regional parties (since they either lack a Delhi presence or just have Rajya Sabha appointees there), while the national leaders, based in Delhi, dominate INC and BJP.

On the BJP side, only Sushil Modi, the deputy chief minister and long-time key figure on the BJP side in the state is widely retweeted from among the party’s politicians, while the two national figures Amit Shah and Narendra Modi remain the key figures who attract retweeting in the state. Nonetheless, while Sushil Modi is the most prolific among major leaders in terms of the extent of talking about issues relevant to the state, his messaging does not get the same level of amplification as some of his other party colleagues including RS Prasad and Giriraj Singh, who tweet more on national issues.

Despite the organization of the parties on the ground around local leaders, the retweeting from the rank and file politicians in the INC suggests that it is the Gandhi siblings and Youth Congress leaders from outside the state who most influence the discourse for the party. This is analogous to the importance of Modi and Shah in the messaging of the BJP.

Of the four parties, only RJD and BJP have strong state party handles with significant following. Both the INC and JDU have limited following for their state party handles, and the INC’s most retweeted handles are all from the center. The prominence of Youth Congress handles (more followed and retweeted than the party’s state handle) suggests that younger leaders are at the forefront of the state’s online outreach.

We find that RJD is generally better organized on social media than JDU. While several RJD leaders boast strong following and retweeting, the JDU’s social media presence is strongly centered around Nitish Kumar, with no other handle representing the party in the state elections having more than 50k followers. On the RJD side, leaders like Tanweer Hassan, Arun Kumar Yadav, Shiv Chandra Ram Chamar all have significant following and retweeting for their messaging. The RJD also has local Twitter handles at the level of each district.

There are similarities between what we see here and other regional parties – when a single family is at the center of the party (Shiv Sena, TRS, YSRCP etc) we find that multiple members of that family are widely followed on social media and drive the traction. Thus, the Lalu Yadav family has at least six widely followed Twitter handles – Lalu, Rabri Devi, Misa Bharti, Tejashwi, Tej Pratap, Raj Lakshmi.

In contrast, when the state party is centered around a single key leader, such as BJD, JDU, AMMK, the social media presence tends to be dominated by an individual. In the JDU, only INC defector Ashok Choudhary has a footprint of over 100k followers in the state.

### Center or State

# Connectivity of politicians (Summary)
