---
title: "Connectivity Dynamics of States & Parties on Twitter"
date: 2020-11-20
tags: [machine learning, graphs, social, data, media]
excerpt: "Machine Learning, Graphs, Social, Data, Media"
header:
  image: "/images/twitter.png"
mathjax: "true"
---
# Connectivity of politicians on Social Media
In this section, we discuss the political engagement of politicians in India on social media from January 2019 to November 2020. By political engagement, we refer to the retweets and mentions made by one politician to some other politician. Hence, each retweet or mention can be thought of as a weighted directed link from politician X to politician Y with edge weight Z (figure 1), denoting that X actively engages with Y on Twitter around Z number of times.
{% include image.html url="/images/connectivity/connectivity.png" description="Figure 1: Active Engagement on Twitter between two politicians X and Y." %}

---

## Methodology
A party (P1) of some state (S1) will comprise of many politicians belonging to that state-party group. Engagement of these politicians will, however, be distributed across the entire network to many other such state-party (S2-P2) groups, including themselves. We have defined the connectivity ratio or connectivity percentage in terms of the edges that leave from one group (S1-P1) to another group (S2-P2), all weighted by their strength of engagement (edge weight). Figure 2 visually shows how the metric has been computed.
{% include image.html url="/images/connectivity/links.png" description="Figure 2: Connectivity between Party-1 of State-1 with another Party-2 of State-2, shown in a bipartite graph representation." %}

Algorithm 1 for computing this metric has been detailed below. In short, we capture the relative weight of the edges that fall from one group (X) to the other (Y) in comparison to the total weight leaving that group (X).
{% include image.html url="/images/connectivity/alg.png" description="" %}

---

## Terminology
Before diving into the connectivity dynamics at state or party, we will discuss the terms that will be broadly discussed throughout this section. Refer to figure 3.
{% include image.html url="/images/connectivity/types.png" description="Figure 3: Different types of connectivity metrics explored in this chapter. Blue denotes all the neighbouring states of the given state X." %}

### Self-Connectivity
Connectivity of the state-party X to itself is termed as 'self-connectivity'. ((S1, P1) $$\rightarrow$$ (S1, P1))

### Neighbourhood Connecitivity
Connectivity of X to its neighbouring states is called 'Neighbourhood Connectivity'. ((S1, P1) $$\rightarrow$$ (['Nbr-1', 'Nbr-2', `Nbr-3'], P1))

### From & To Center Connectivity
We have defined Delhi to be the 'Center' state since all the union ministers (Prime Minister and Council of Ministers), party leaders and important politicians operate from there. Connectivity of X to the 'Center' state ((S1, P1) -> ('Delhi', P1)) is termed as To Center Connectivity, while connectivity of the 'Center' to X is termed as From Center Connectivity (('Delhi', P1) -> (S1, P1)).

---

## State Connectivity
In this section, we talk about the connectivity of states in India and the engagement of the politicians in a given state with politicians of other states, center and the neighbouring states.

### State to State Connectivity
Figure 4 denotes the important state to state relationships in terms of their political connectivity over the duration of 23 months (Jan, 2019 to Nov, 2020). For each state, we consider all the politicians from all the parties. Delhi state includes all the national party heads who operate from there, and as well as the Prime Minister's Council of Ministers which includes the Cabinet Ministers, Ministers of States, etc. With Delhi acting as the Center, we can see the involvement of the states in establishing a significant amount of social media interactions with the Center.

{% include image.html url="/images/connectivity/state-state.png" description="Figure 4: State to State Connectivity of major states with at least 300 politicians. All other states have been clubbed together under the category of 'Others'. The band shows the percentage of politicians of one state that are actively engaged to politicians in the other states. The threshold considered for each band link is set at 2% of the total number of connections from that state. The width of the circular arc denotes the band of connectivity left after removing 'self', and the height denotes the number of politicians from the states, with minimum number of 284 politicians in Andhra Pradesh and maximum number of 2533 politicians from the state of Maharashtra. There are two shades of opacity of the bands- darker shades are used to highlight the non-center relationships between the states, and the lighter ones are used to denote the role of `Delhi' as the center." %}

Important non-center relationships between the states (shown in dark shade) also emerge out on social media, for example, Telangana and Andhra Pradesh, Kerala and Karnataka, Punjab and Haryana, etc. Such states may seem to connect on the basis of their shared culture, language, party presence and geography, amongst others. We also see that states like Uttar Pradesh, Karnataka and Maharashtra hold strong political relationships to other states, which shows their political importance as highlighted on social media.

---

{% include image.html url="/images/connectivity/state-distribution.png" description="Figure 5: Distribution of states connectivity into 4 sections -  connectivity to self, connectivity to center, connectivity to the neighbouring states and connectivity to the rest of the states. Center (Orange) consists of the politicians from Delhi. For Uttar Pradesh and Haryana, Delhi has been excluded as their neighbouring state while computing the Neighbourhood connectivity (Green)." %}

Figure 5 highlights the distribution of a state's connectivity to itself, to the Center (Delhi), to its neighbouring states and to the rest of the country. We see that the most self-connected states are from the South (Tamil Nadu, Karnataka and Andhra Pradesh), and the least self-connected states are the UTs (Chandigarh) and the states from the North-East (Tripura, Manipur, Arunachal Pradesh). Interestingly, Kerala from the South has low self-connectivity which can due to the strong presence of INC there. Uttar Pradesh and Haryana have a strong neighbourhood connectivity due to the presence of Delhi as a neighbour. Apart from these two, states in the north are in general more connected to their neighbours than the ones in south or north-east. North-eastern states are, in fact, more politically engaged to the rest of the country than their immediate neighbours. Another trend that we see is that as the self-connectivity of states decreases, their connectivity to the center gradually increases. We further explore this trend further in the next section.

---

### Role of Center
{% include image.html url="/images/connectivity/self_to_center.png" description="Figure 6: Comparison of the self-connectivity of various states in India to the connectivity at the center (Delhi). States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians." %}

We see an inverse linear trend between a state's connectivity to the center and to itself (figure 6). This is to say that when a state starts to get more and more politically engaged with itself, it systematically decreases its attention given to the center. We see a similar pattern for the parties also in the later sections of this chapter. Gujarat comes out as an outlier state in this case, i.e. it maintains a high self-connectivity while also engaging fairly well with the center. Some other outliers are north-eastern states which do not fit this pattern and are highlighted in green in the figure. While Arunachal Pradesh (AR) and Assam (AS) engage more with the center than Manipur (MN), Tripura (TR) and Nagaland (NL), the former group manages to stay better self-connected than the latter. As mentioned earlier, strongly self-connected states are from the South which are Tamil Nadu (TN), Andhra Pradesh (AP), Karnataka (KA) and Telangana (TS). In this figure, the bubble size denotes the number of politicians in each state. We notice that the states with high self-connectivities usually have a large set of politicians, while states with weak political representations seems to engage more with politicians outside the state, and more preferably, the center.

{% include image.html url="/images/connectivity/state_from_to_center.png" description="Figure 7: Comparison of the connectivity to center of various states in India to the connectivity from center. States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians." %}

Figure 7 measures this disparity of the role played by center, and more specifically, it highlights the states that get more engagement from the center with respect to their engagement to the center. While states like Rajasthan (RJ), Madhya Pradesh (MP), Karnataka (KA), Maharashtra (MH) and Uttar Pradesh (UP) provide roughly the same engagement to the center, only UP gets preferentially the most attention from the center. This can be because UP, being a BJP ruled state, has been a hug of huge political attention from the BJP-ruled center after Hathras and Ram Mandir inauguration. We see most of the states that receive the most attention from the center are from the northern-central belt, which includes states like UP, MP, Rajasthan, Gujarat, Bihar and Haryana. Maharashtra received a similar attention from the center after state legislative assembly elections in late 2019, and the death case of Sushant Singh Rajput (SSR). Tamil Nadu (TN), being a strongly self-connected state, didn't engage much with the center and nor did it receive any attention from the center. North-Eastern states engage a lot to the center, but do not receive any attention from the center. Similarly, almost all southern states (except Karnataka) receive low attention from the center.

---

### Engagement with a State

{% include image.html url="/images/connectivity/eng_with_state.png" description="Figure 8: Temporal variation of the states most engaged by the politicians in India. States with a minimum engagement share of 2\% across all bimonthly time periods have been considered." %}

Figure 8 shows the engagement with a particular state by all the politicians in the country. The most engaged states by Indian politicians include Delhi, Maharashtra, Uttar Pradesh and Gujarat. Maharashtra occupies a significant share of political attention in India in 2019 during Lok Sabha and Legislative Assembly Elections. Rajasthan received the major attraction in May-June 2020 over the claims by the CM against BJP making poaching attempts against its MLAs. UP remained in the limelight in the second-half of 2020 period after Hathras case and Ram Mandir inauguration. It is interesting to see that only a limited number of politically active states receive attention in the Indian politics, and most of the other states are often left ignored without receiving any much engagement on social media.

---

### Self and Neighbourhood Connectivity
Figure 9 shows the relationship between the connectivity of a state with its neighbours and the connectivity within itself. Haryana and Uttar Pradesh tends to be strongly engaged with their neighbours because of Delhi, and stands as outliers in the graphs.

{% include image.html url="/images/connectivity/self_nbr.png" description="Figure 9: Comparison of the self-connectivity of various states in India to the connectivity of their neighbours. States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians." %}

---

## Party Connectivity

### Party to Party Connectivity
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/party-party-final2.png)
Party to Party Connectivity of major parties with at least 50 politicians. All other parties have been clubbed together under the category of `Others'. The band shows the percentage of politicians of one party that are actively engaged to politicians in the other parties. The threshold considered for each band link is set at 3% of the total number of connections from that party.

---

![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/party-distribution.png)
State wise distribution of parties' connectivity to itself within the same state. For each state, only those regional parties have been considered you get at least 3% vote share in the last state assembly elections as per the EC data. BJP & INC have been included for each state so as to compare the state-wise representation of regional and top national parties.

---

![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/Dominance_in_Self_Connectivity.png)
Indian Map highlighting the states where state parties are well connected within the state (shown in red) than the top national parties (BJP and INC) which is shown in blue.

---

### Role of Center
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/party_to_from_center.png)
Comparison of the connectivity to center of various parties in India to the connectivity from center. Parties have been color coded into their respective category as per the definition defined by the Election Commission of India (ECI). Parties with at least 3% vote share for each state's assembly election have been considered.

---

### Engagement with a Party
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/eng_with_party.png)
Temporal variation of the parties most engaged by the politicians in India. Parties (National & Regional) with a minimum engagement share of 0.5% across all bimonthly time periods have been considered.

---

### Self Connectivity of Parties
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/party-distribution2.png)
Comparison of the connectivity values of various parties in India to the politicians of their own party, to BJP, to INC and to other remaining parties. Only top parties with at least 3% representation of vote share in state assembly elections have been considered, along with all the recognised national parties.

---

