---
title: "Leveraging Graph Algorithms to Predict Congressional Political Activity through Campaign Finance Networks"
excerpt: "<br/><img src='/images/full_net.png'>"
collection: portfolio
---
In 2010, the Supreme Court's ruling in Citizens United v. Federal Election Commission removed long-held restrictions on corporate campaign contributions to political action committees (PACs). Since 2010, there has been a significant increase in political contributions as well as lobbying activity.


While campaign finance data is accessible through information requests and bulk data requests, it is difficult to determine how campaign contributions influence political activity by simply analyzing the data without linking together subsidiaries and parent companies, as well as congressional members to affiliated PACs.


Therefore, I created a network of connections between congressional members, corporate donors, affiliated PACs, lobbying firms, and congressional bills. This network was created by accessing bulk data and APIs from from OpenSecrets, the FEC, and Congress.gov.


Below is a visualization of the connected network for members on the House Ways and Means Committee and their connections to bills and corporate donors. The corporate donors are categorized by industry:


<br/><img src="/images/full_net.png" width="600" height="400">


As a subset of the full network, I extracted the bipartite network of corporate donors to congressional members (edges weighted by normalized contribution amounts): <p>


<br/><img src="/images/bipartite.png" width="500" height="300">


 From the bipartite network, I aimed to evaluate bill sponsorship prediction capability of the network. By leveraging **collaborative filtering**, a technique primarily used in recommender systems, I generated various one-mode projections from the bipartite network using custom node similarity schemes, such as weighted Jaccard index. 



<br/><img src="/images/bip_proj.png" width="600" height="400">

Using the projected networks, I predicted that each node (congressional member) would cosponsor legislation sponsored by their k most similar nodes. The following graph shows that when compared to a random baseline, the network information from the similarity schemes consistently improved precision at predicting which bills the congressional members would sponsor or cosponsor.



<br/><img src="/images/bill_prec.png" width="600" height="400">


A similar method was used to predict the party affiliation for each member. The Weighted Jaccard prediction scheme vastly outperformed the random baseline and other similarity methods, achieving > 80% precision when limiting the prediction method to considering only the party of 3 most similar members.



<br/><img src="/images/party_pred.png" width="600" height="400">







