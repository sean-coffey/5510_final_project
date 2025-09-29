# 5510 Final Project - Unsupervised Learning on Country Data

Kaggle: https://www.kaggle.com/datasets/rohan0301/unsupervised-learning-on-country-data

For this project, I wanted to find a simple dataset that I could use to explore the various unsupervised learning techniques that we've been learning in the lectures. In particular:

1) Principal Component Analysis - To investigate how to understand and interpret the principal components. The maths/functions to generate them are simple enough, but I want to improve my ability to relate the resulting components to the original features and to visualise them in ways that help understanding.
2) K-Means Clustering - Generating them is straightforward. My objectives are to find out more about how to optimise the number of clusters, how to score them, and how to visualise them.
3) Comparison with other clustering methods - A secondary objective, time allowing.  

The more I study these ML methods, the more I find that the code generation, albeit with the assistance of AI, is not the issue. I have no qualms about using AI, the tools are here we need to learn how to deploy them effectively. However, I do want to focus on: effective usage, interpretation of results, drawing conclusions, understanding parameters clearly, in order to avoid the many rabbit holes associated with complex libraries such as scikit-learn.
If I am able to generate a reasonably meaninful clustered description of the Country Data based on the socio-economic features therein and achieve these learning objectives, I will consider the project a success.

A Note on Project Setup
As we do these learning projects, I am trying to build a library of functions that will help me complete basic EDA and preprocessing quickly and efficiently. That is why there is so much code in the Project Setup section.


#### Objective from Kaggle: Clustering the Countries by using Unsupervised Learning for HELP International.

To categorise the countries using socio-economic and health factors that determine the overall development of the country.

#### About organization:

HELP International is an international humanitarian NGO that is committed to fighting poverty and providing the people of backward countries with basic amenities and relief during the time of disasters and natural calamities.

#### Original Problem Statement:

HELP International have been able to raise around $ 10 million. Now the CEO of the NGO needs to decide how to use this money strategically and effectively. So, CEO has to make decision to choose the countries that are in the direst need of aid. Hence, your Job as a Data scientist is to categorise the countries using some socio-economic and health factors that determine the overall development of the country. Then you need to suggest the countries which the CEO needs to focus on the most.

#### For this Project

I am going to focus on finding a clustering solution that separates countries into groups based on their socio-economic and health factors. I am not focused on using this result to make recommendations about aid.



## Analysis and Thoughts after completing the Project

1) Whilst the optimal number of clusters is 2 according to the scoring (irrespective of which clustering methods are used), a k-Means cluster solution with 5 clusters is more informative and intuitively understandable.
2) Outlier treatment is critical, especially with k-Means clustering. The combination of log-scaling, winsorization and RobustScaler proved an effective way to deal with the outliers whilst retaining the essential characteristics of the data.
3) Spending time on understanding the principal components before clustering was highly worthwhile. (a) It helped data understanding, (b) without this exercise, I would not have spotted a critical error in my original pre-processing: namely, that the log transformations changed the column order, which made the resulting analysis incorrect.
4) Visualising the clusters using PCA bi-plots is a powerful way to understand the data. The two techniques employed (a) adding vectors representing the original features and (b) adding hulls to quickly visualise cluster separation with multiple principal component combinations were both effective tools that I willl reuse going forward.
5) Naming Clusters was hard. It required me to go beyond the visualizations and supplement this with a comprehensive detailed print out of the cluster information. The time spent was worthwhile, in terms of the understanding I gained. I'm still an amateur when it comes to naming, but this will improve with practice.
6) I would have needed to spend more time on the DBSCAN model and the Hierarchical Clustering model to understand their strengths and weaknesses. However, given the time constraints, this will have to be deferred to next steps.
7) I am not yet comfortable with the basic issue with unsupervised learning: there are not easily available checks (predict, RMSE scoring, statistical significance,...) to validate the results. I will need to spend more time on this.

## Conclusions

A combination of outlier handling, PCA transformation and k-Means clustering was able to identify five clusters in the data: separated by the features of interest, and intuitively understandable.

The cluster I named "Least Developed Countries" probably is a good target set for the CEO of HELP Organisation to focus aid investment (see Introduction). However, whilst the data and clustering captures socio-economic need, it does little to help understand how effectively the aid could be deployed or the likely impact of the investment. I would want to do further modelling of these aspects before making any firm recommendations.

As a learning exercise, this project was excellent. I feel I have substantially moved my understanding of unsupervised learning techniques forward. In particular, I would call out:
 - Handling outliers with differing scaling techniques and Winsorization.
  - PCA understanding and interpretation (with loading tables and charts to describe the principal components)
  - K-Means scoring to find optimal number of clusters using a basket of scoring metrics
 - Visualisation of clusters using PCA bi-plots (with feature vectors and hulls).
  - Time spent on understanding and interpretation should outweigh time spent on code generation.