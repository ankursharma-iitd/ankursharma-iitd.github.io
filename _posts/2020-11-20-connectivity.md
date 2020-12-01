---
title: "Taxonomy of Indian Politics on Twitter - State-by-State analysis & Connectivity Dynamics"
date: 2020-11-20
tags: [machine learning, graphs, social, data, media]
excerpt: "Machine Learning, Graphs, Social, Data, Media"
header:
  image: "/images/twitter.png"
mathjax: "true"
---
# Connectivity of politicians

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
We plotted the difference between the extent to which parties retweeted other politicians from their own party from within the state, from any location outside of their own state, from the capital, or of their main leader. The goal of this distinction is to see the relative prominence of leaders from the capital as against those in the state, especially the key leader of the party, in the party’s outreach.

We see, for instance, the two regional parties tend to have a higher share of retweeting among the parties’ politicians of their key leaders – thus Tejashwi Yadav tends to dominate the RJD’s tweets, whereas Nitish Kumar accounts for a significant share of the retweets by the JDU. This rate of retweet is much higher than in the national parties, in some periods as much as half of all retweets by all the politicians by their respective parties are just of the two leaders’ accounts. This underlines the centrality of the key leaders in driving the entire online presence of the party.

We find that in the case of the INC and BJP, the national parties, there is much more retweeting of both politicians from the national party based in other states, as well as of either the key leader (Narendra Modi, Rahul Gandhi) or other party leaders based in Delhi. Rahul Gandhi gets marginally less retweeted among his own party than Narendra Modi gets among his party members, something that is also seen in [other research](https://www.microsoft.com/en-us/research/publication/leader-or-party-personalization-in-twitter-political-campaigns-during-the-2019-indian-elections/).

{% include image.html url="/images/connectivity/4.jpg" description="Figure 3: Visualization of tweeting growth and retweeting of their own colleagues by politicians in the four main parties in Bihar between 2015-2020" %}

### Timelines of Social Media Activity
The visualizations in figure 3 above show the yearly progression of social media use by politicians in Bihar since 2015. Thus, while all the parties had a fairly small presence in 2015, it had grown significantly by 2020, though the dominating share of total activity was still with the two national parties. The dominant retweeting of out-of-state politicians by INC and BJP suggests that the discourse and strategy may be more driven by headquarters than the states.

The dominance of the INC and BJP in 2020 is also worth noting. While the RJD does have a significant presence, and a particularly high rate of retweeting, possibly explained by a fairly tight knit core group of followers, it does not have the scale of the BJP or INC on Twitter.

Turning to more recent data, in figure 4, we see some patterns around the points when the use of social media by politicians increases. We see there is an increase in tweeting (and retweeting of their party leaders) by the parties during the general elections, and an increase in social media activity during the COVID19 crisis.

{% include image.html url="/images/connectivity/5.jpg" description="Figure 4: Temporal frequency of tweeting by four key Bihar political parties between Jan 2019 to Sep 2020" %}

We also see here that while the elections and Covid drove high engagement among politicians across parties – both for the health-related reasons and due to criticism of the government due to the migrant crisis, many of whom were from the state. The high engagement with Chandrayaan and CAA/NRC was mainly restricted to BJP politicians.

### Topical Patterns

For the ease of visualization, we plotted the most used hashtags in 2020 on a spectrum between NDA (BJP+JDU+LJP) and non-NDA (INC+RJD), although the BJP clearly dominates the NDA list of hashtags. We see here there are patterns that are closely related to the larger social media related messaging throughout the country. For one, we see that the NDA politicians dominate the more retweeted hashtags, in some part because these hashtags tend to have more of a broadbased national appeal – such as MannKiBaat and IndiaFightsCorona. We also see that #BiharFightsCorona modeled on the BJP’s various coronavirus-related hashtags. We find that the more polarized hashtags – such as “RozgarDo” or “SpeakUpForDemocracy” on the non-NDA side, or hashtags related to the Citizenship Amendment Act on the NDA side tend to be largely used by one side or the other. We find in Bihar that the national parties tend to tweak for local purposes their overall national strategies. Thus the ‘Atmanirbhar’ branding that has been central to BJP’s messaging is also used in Bihar, while similarly tweets using the term ‘Berozgar’ to attack the economic impacts of the BJP government in other settings by the INC are used here as well

{% include image.html url="/images/connectivity/6.jpg" description="Figure 5: Polarity of key hashtags on Twitter, based on the extent of their use by NDA or non-NDA politicians in Bihar, arranged by the frequency of use by politicians between January and October 2020." %}

We also find that hashtags about the state, ie using the word ‘Bihar’, बिहार , NitishCares, NitishKumar4SSR, NitishKumar,BiharRejectsNitish, BiharBerojgarBadloSarkar, BJPWithBihar, ModiCares4Bihar, BiharBole_RozgarDo, बिहार_को_मत_बनाओ_वुहान are much more used starting mid-2020 compared to earlier,  with a corresponding decline in the use of hashtags about India. This suggests that as the state moves towards elections, politicians likewise focus on the state over the larger nation-state.

### Influencers
Much recent work has noted the importance of celebrity influencers in political outreach. We find that the polarization of celebrities that one sees at the national level is fairly comparable to what one sees in Bihar. BJP politicians are generally the most likely to engage with celebrities as part of their outreach strategies, while JDU politicians generally do not retweet celebrities as much. We see for instance that none of the most retweeted celebrities are from Bihar – folk singer Malini Awasthi who performs in Bhojpuri is possibly the closest to a celebrity in the state.

We see in the colour coding of the retweeting that celebrities popular with the BJP including Babita Phogat, Vivek Agnihotri, and Akshay Kumar. The most retweeted outlier is Payal Rohatgi, whose popularity is in part driven by her partisan engagement with pro-BJP content, but also with conspiracy theories related to the death of actor Sushant Singh Rajput, the late actor from Bihar, whose demise briefly became a major issue in the state elections.

{% include image.html url="/images/connectivity/7.jpg" description="Figure 6: Celebrities and Influencers most retweeted by Bihar politicians across for key parties between January 2018 and October 2020." %}

We see that on the other end of the spectrum, some of the celebrities engaged are generally polarized against the BJP  thus comedian Kunal Kamra, actor Swara Bhaskar and filmmakers Anurag Kashyap and Vinod Kapri. We see another pattern here, that both the INC and RJD tend to retweet these celebrities, while the BJP and JDU eschew them. We see that most celebrities who are widely retweeted by politicians seem polarized either towards or away from the one or another political party, suggesting that the alignment of views of the celebrity with the party (or its position on the perceived antagonist party) is an important driver of political engagement.

The exceptions to this rule are either the superstars with large, broad-based following such as Shahrukh Khan, Amitabh Bachchan and Salman Khan, or in this case, the actor Sonu Sood, who gained attention for his charity work during the migration crisis following the Covid lockdowns.

### Mainstream Media Engagement

We plotted the retweeting of mainstream media commentators on Twitter by Bihar politicians. We find that there are some patterns in which parties engage which journalists or public commentators. Most journalists either tend to be preferred by the NDA (and here, primarily the BJP since the JDU has fairly limited engagement with journalists), or by the non-NDA side, which is seen in the significant overlap between the RJD and the INC in which journalists their Bihar politicians tend to prefer. Journalists who tend to be from channels or have pro-ruling party content including Rohit Sardana, Deepak Chaurasia, Shefali Vaidya, Suresh Chavhanke, Chitra Tripathi, Sudhir Chaudhary, and Anjana Om Kashyap.

{% include image.html url="/images/connectivity/8.jpg" description="Figure 7: Journalists most retweeted by politicians from INC, BJP, RJD and JDU in Bihar in 2020, annotated by instances of tweets being circulated and total number of politicians engaged" %}

On the other hand, journalists or commentators who tend to lean on the antiestablishment end including Saket Gokhale, Prashant Kanojia, Rohini Singh, Punya Prasun Bajpai tend to be more tweeted by INC and RJD. Interestingly, most of the journalists are Delhi-based, very few of the widely retweeted journalists work for the local press or are based in Bihar as part of their work, though some journalists like Punya Prasun Bajpai and Ajit Kumar are from Bihar. The only account that is tweeted significantly across party lines is the (since blocked) account of journalist and caste activist Dilip Mandal.

{% include image.html url="/images/connectivity/9.jpg" description="Table 2: Politicians most engaged with journalists from the four key Bihar parties" %}

One general pattern we see is that the JDU is a lot less engaged with journalists than the three other parties. We see that each party has a small number of politicians who engage the public through retweeting journalists. Here, we see an important distinction between the approaches of the regional parties and the national parties. In both INC and BJP, the politicians who engage the most with mainstream journalists tend to be younger politicians or those associated with IT cells or youth wings.

In contrast, in the RJD, though to a lesser extend in the JDU as well, the politicians who engage most with journalists’ content are among their more senior and widely followed leaders.
From RJD, Misa Bharti, the Rajya Sabha MP and a key party leader was the most active in engaging journalists, and the party’s main handle. She has in fact been consistent in engaging mainstream media content, other work has shown that she and Asaduddin Owaisi were the most active in amplifying mainstream media content among their followers. The RJD was the only party among these whose official party handle (@RJDforIndia) was among the five most active in their party in putting out journalistic content.

### Methodology
We analysed Twitter Tweets data from Bihar politicians, extracted from the [Nivaduck dataset](https://www.microsoft.com/en-us/research/publication/nivaduck-a-scalable-pipeline-to-build-a-database-of-political-twitter-handles-for-india-and-the-united-states/). Since our target was limited to the position of institutional actors, we do not follow the general public’s Twitter handles, but rather people with political parties. For politicians, from the state-party annotated dataset of more than 36000 politicians in India, we identified 1036 Bihar politicians active on social media, and having tweeted anytime from 13th October 2009 to 30th September 2020.
We pulled 2503737 tweets of politicians. To populate journalists and influencers, we used an annotated dataset of 2601 journalists and 1374 influencers, based on our own [past work](http://joyojeet.people.si.umich.edu/celebrity-or-journalist-who-do-indian-politicians-prefer-to-engage/).

Note that this blog has been adapted from Joyojeet's [blog](http://joyojeet.people.si.umich.edu/twitterbihar/) which details our work.
