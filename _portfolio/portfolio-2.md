---
title: "Using Machine Learning to Predict Michigan Healthcare Pricing with Insurance Data"
excerpt: "<br/><img src='/images/michigan_prices.png'>"
collection: portfolio
---

In 2021, the Center for Medicare and Medicaid Services required hospitals to provide clear,
accessible pricing information about the items and services they provide in a machine-readable
format.


However, many of these files - called chargemasters - are locked in difficult to parse PDFs. An online community was able 
to crowd source data entry from these PDFs to create structured [datasets](https://www.dolthub.com/repositories/dolthub/transparency-in-pricing) which include information about hospitals across the US and their negotiated rates with various insurance companies for provided items/services.


For citizens and foreigners alike, insurance industry practices are opaque and hospital prices can vary dramatically in different regions of the United States. The recent publication of the wealth of structured data can be used as inputs to ML models to make inferences about hospitals, insurance companies, and prices.


The aim of this project was to predict the price of a given item on a Michigan hospital’s chargemaster using data from the insurance company (payer), the description of the item/service, and demographic information about the hospital’s location.


The above dataset includes zip codes for each hospital, which were joined with demographic data from
[Census](https://www.census.gov/) such as % of Population over 65, % of Population with Health Insurance, 
and Median Income. 


Below are plots of average price per item/service (averaged across hospitals in each county) in Michigan
included in the dataset as well as median income.


<br/><img src="/images/michigan_prices.png" width="600" height="300">


<br/><img src="/images/median_income.png" width="600" height="300">


Each item/service included a text desciption feature which were not standardly aligned across hospitals.
I used the [BioLord Transformer](https://huggingface.co/FremyCompany/BioLORD-2023-S)
model to vector embed the descriptions, which were then categorized using birch clustering. 


The transformer was particularly effective since it was trained on a medical corpus.


Below is a T-SNE visualization of the vector embeddings:


<br/><img src="/images/embeddings.png" width="500" height="300">


The associated cluster was used as a feature along with the aforementioned features (demographic data, insurance company)
as inputs to various ML models, such as a Random Forest, XGBoost, and Neural Network. In the results below, the Neural
Network had the best RMSE when predicting the price of a given item/service for a specific insurance company.


<br/><img src="/images/results.png" width="500" height="300">


The Neural Network performed better than the basline, which provides evidence that medical 
pricing is somewhat dependent on the socioeconomic factors of a hospital, the derived category of service provided,
and the insurance company. However, the relatively high RMSE indicates that given this information,
it is difficult to predict the exact cost incurred by patients in the Michigan healthcare system.








