# Machine Learning with Java - Part 3 (k-Nearest Neighbour)!

In my previuos articles, we have discussed about the linear and logistic regressions.This article focuses on the k nearest neighbour algorithm usage with java.

# Nearest Neighbour

Nearest Neighbour is also called as Instance-based Learning or Collaborative Filtering.It is a useful data mining technique which allow us to use our past data with known output values to predict an output value for the new incoming data. 

# Difference with Regression and Classification

Let us consider the company Flipkart and the common that the customer who purchased the product X also purchased the product Y.If we use classification algorithm to classify this scenario, we will end up in infinite no of branches and nodes.The tree will be too big and accuracy also we cannot say.Even if we have single branch, we will end up in only 3 products. But flipkart will show us 10-12 products in recommendation section.

Nearest neighbour will fix the above problems in a very efficicent manner.It's not limited to any number of comparisons. It's as scalable for a 10-customer database as it is for a 10 million-customer database, and we can define the number of results we want to find. It will be the most useful for anyone reading this who has an e-commerce store.

# Concept with Nearest Neighbour

We have an customer data below to predict the output for the unknown data. In this case, we are going to find the recommendations for the customer with the input data age and income. The ultimate goal is to find what are all recommendations we can give for the customer who is of 58 year ond with monthly salary as 51k.

Customer       Age      Income     Purchased Product

1               25        46k           Book

2               39        100k          TV

3               35        38k           DVD

4               69        150k          Car Cover

5               58         51k             ???



We have to calculate the distance first and then based on the k value, we can give them nearest k neighbours.
The formula will be SQRT (( ((input income age - Age)/(highest age-lowest age))^2) + ((input income data - Income)/(highest income -lowest income ))^2)

By default the k value is 1, we can pass the value of k while creating the instance. If the value of k is 1, it will display 1 product (1 nearest neighbour) and if the value of k is 2 , it will displays the 2 products.Using the above example, if we want to know the two most likely products to be purchased by Customer No. 5, we may conclude that they are books and a DVD based on the formula.

# Lazy Learning and Eager Learning

K-nearest neighbors is a lazy learning algorithm. KNN is a typical example of a lazy learner. It is called lazy not because of its apparent simplicity, but because it doesn't learn a discriminative function from the training data but memorizes the training dataset instead.

Eager Learning is opposite to Lazy Learning, in which the system tries to construct a general, input-independent target function during training of the system,where generalization beyond the training data is delayed until a query is made to the system.The last 2 articles we have seen is of eager learning type.



# demo

@[Luke, how many stars are there in these galaxies?]({"stubs": ["src/main/java/com/yourself/Universe.java"], "command": "com.yourself.UniverseTest#test"})

Check out the markdown file [`welcome.md`](https://github.com/TechDotIO/java-template/blob/master/markdowns/welcome.md) to see how this exercise is injected into the template.

# Code Explanation


# Challenges with this model 

The power of Nearest Neighbor will be efficient with large amount of data like flipkart with 10 billion customers, since they are likely many potential customers in their database with similar habbits like the predicting customer.

The model breaks down quickly and become inaccurate when we have only few data points for the compariosion.The product recommendations will not be accurate in this case.

The one more challenge is , In Flipcart 10 million users, each customer must be calculated against the other 10 million customerto find the nearest neighbour.First, if our business has 10 million customers, that's not technically a problem. Second, these types of computations are ideal for the cloud in that they can offloaded to dozens of computers to be run simultaneously, with a final comparison done at the end. (Map Reduce) Third, in practice, it wouldn't be necessary to compare every customer in Flipkart's database to myself if I'm only purchasing a book. The assumption can be made that I can be compared to only other bookbuyers to find the best match, narrowing the potential neighbors to a fraction of the entire database.

Note: The data used here is just for an example, it is not a real ones. 
The example demo also to just showcase how to use the algorithm.

