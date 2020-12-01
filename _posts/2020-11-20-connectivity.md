---
title: "Connectivity Dynamics of States & Parties on Twitter"
date: 2020-11-20
tags: [machine learning, graphs, social, data, media]
excerpt: "Machine Learning, Graphs, Social, Data, Media"
header:
  image: "/images/twitter.png"
mathjax: "true"
---
# Connectivity of politicians

## State Connectivity

### State to State Connectivity
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/state-state-final2.png)
State to State Connectivity of major states with at least 300 politicians. All other states have been clubbed together under the category of `Others'. The band shows the percentage of politicians of one state that are actively engaged to politicians in the other states. The threshold considered for each band link is set at 3% of the total number of connections from that state. The width of the circular arc for each state denotes the number of politicians in that state, with minimum number of 272 politicians in Andhra Pradesh and maximum number of 2493 politicians from the state of Maharashtra.

---


![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/state-distribution.png)
Distribution of states connectivity into 4 sections -  connectivity to self, connectivity to center, connectivity to the neighbouring states and connectivity to the rest of the states. Center (Orange) consists of the politicians from Delhi. For Uttar Pradesh and Haryana, Delhi has been excluded as their neighbouring state while computing the Neighbourhood connectivity (Green). 

---

### Role of Center
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/from_to_center.png)
Comparison of the connectivity to center of various states in India to the connectivity from center. States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians.

---

### Engagement with a State
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/eng_with_state.png})
Temporal variation of the states most engaged by the politicians in India. States with a minimum engagement share of 2% across all bimonthly time periods have been considered.

---

### Self, Center and Neighbourhood Connectivity
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/self_to_center.png})
Comparison of the self-connectivity of various states in India to the connectivity at the center (Delhi). States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians.

---

![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/self_nbr.png)
Comparison of the self-connectivity of various states in India to the connectivity of their neighbours. States have been color coded into their respective zones as per the definition defined by the Ministry of Home Affairs. Each state here has at least a representation of 50 politicians.

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
![alt]({{ site.url }}{{ site.baseurl }}/images/connectivity/party-distribution2.png}
Comparison of the connectivity values of various parties in India to the politicians of their own party, to BJP, to INC and to other remaining parties. Only top parties with at least 3% representation of vote share in state assembly elections have been considered, along with all the recognised national parties.

---

