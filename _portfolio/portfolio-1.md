---
title: "Using Campaign Finance and Lobbying Network to Predict Congressional Political Activity"
excerpt: "<br/><img src='/images/full_net.png'>"
collection: portfolio
---

<p>In 2010, the Supreme Court's ruling in Citizens United v. Federal Election Commission removed long-held restrictions on corporate campaign contributions to political action committees (PACs). Since 2010, there has been a significant increase in political contributions as well as lobbying activity.<p>

<p> While campaign finance data is accessible through information requests and bulk data requests, it is difficult to determine influence of campaign contributions on political activity by simply analyzing the data at a singular connection granularity. 

Therefore, I created a network of connections between congressional members, corporate donors to their politcal campaigns and affiliated PACs, corporate donations to lobbying firms, lobbying firm activity on specific bills, and congressional member sponsorship and cosponsorship of specific bills. This network was created by accessing bulk data and APIs from from OpenSecrets, the FEC, and Congress.gov.<p>

<p> A visualization of the connected network for members on the House Ways and Means Committee: <p>

<p><p>

<img src="images/full_net.png" width="400" height="200">

<p> A toy bipartite network of corporate donors to congressional members (edges weighted by normalized contribution amounts): <p>

<p><p>

<img src="images/bipartite.png" width="400" height="200">

<p> From the bipartite network, I aimed to evaluate bill sponsorship prediction capability of the network. By leveraging **collaborative filtering**, a technique primarily used in recommender systems, I generated various one-mode projections from the bipartite network using custom node similarity schemes, such as weighted Jaccard index. <p>

<p><p>

<img src="images/bip_proj.png" width="400" height="200">

<p> Using the projected networks, I predicted that each node (congressional member) would cosponsor legislation sponsored by their k most similar nodes. The following graph shows that when compared to a random baseline, the network information from the similarity schemes consistently improved precision at predicting which bills the congressional members would sponsor or cosponsor. <p>

<p><p>

<img src="images/bill_prec.png" width="400" height="200">

<p> A similar method was used to predict the party affiliation for each member. The Weighted Jaccard prediction scheme vastly outperformed the random baseline and other similarity methods, achieving > 80% precision when limiting the prediction method to considering only the party of 3 most similar members.

<p><p>

<img src="images/party_pred.png" width="400" height="200">







