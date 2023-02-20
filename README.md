# Cryptocurrencies

#### Overview
The goal of this project was to create a report for an investment bank detailing the cryptocurrencies that are actively trading on the market. Their goal is to create portfolios of available currencies based on their similarities. Because there are a large number of possible cryptocurrencies, and it would take a very long time to individually analyze each one, I decided to implement unsupervised machine learning procedures in order to determine how the currencies are clustered. This would then allow the investment bank to analyze the clusters when creating their portfolios, instead of each currency.

#### Methods
In this case, I did not know in advance how many obvious clusters there were in the data. To start, then, I imported the data and loaded them into a dataframe. This allowed me to easily pre-process the data, such as filtering for those currencies that are actively trading and those that have actually been mined. I then dropped those columns from the dataframe that were unlikely to have any significant impact on the relationships between the data points, such as their names. Leaving such columns in the data could actually interfere with the machine learning process, leading to inaccurate results. 

Because some of the columns that I wanted to consider contained string values, I used one-hot encoding to convert them to numeric values. This was necessary, as the next major step was to scale the data with sklearn's StandardScaler method. Scaling the data prevents those values with greater raw numbers from being given unnecessary weight or consideration by the unsupervised model. With the data scaled, I was then able to determine the three principal components. Principal component analysis is a complex process that involves a lot of linear algebra, specifically linear transformations based on eigenvectors and their eigenvalues. The precise details are beyond the scope of this initial analysis. It suffices to say that effective Principal Compenent Analysis packages have been created for use in Python. In the event that the results are determined to be wrong, digging deeper into the math behind the process could be warranted. 

#### Results
Using K-Means clustering, I determined that k = 4 clusters would best suit the data. This is usally done by finding the 'elbow point' in a graph that shows the results of considering various numbers of clusters. Generally, the elbow point is the point of diminishing returns for including greater numbers of clusters. Indeed, including too many clusters can make the results difficult to understand or communicate.

![K-Means Elbow Point]()

Because there were three principal components I used to organize the data into four clusters, I determined that it would be best to present the results in a 3D scatterplot. 

![3D Scatterplot of Clusters]()

Finally, I wanted to show how the number of coins mined versus the total coin supply could be used to predict the class, or cluster, in which a given coin would be found. This was easy enough to do in a 2D scatterplot, with each cluster represented by a different color. 

![Mining versus Supply]()
