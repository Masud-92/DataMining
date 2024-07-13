# DataMining

                        Customer value analysis for airlines 
      Using K-means Clustering, Decision Tree Classifier, and Support Vector Machine(SVM)

Background of the project
Analyzing customer value in the airline sector includes categorizing customers by factors like how often they fly, the distance they travel, and how much they spend. These divisions assist in recognizing valuable customers and customizing marketing tactics accordingly. Customer segmentation, a widely used method in this scenario, categorizes clients into different segments according to their actions and importance to the organization. Data mining offers efficient tools for carrying out segmentation and analysis.

Due to the rise of the information age, marketing strategies have transitioned from being centered on products to being centered on users, leading to a greater emphasis on customer relationship management (CRM) for companies. Customer classification is a crucial element of CRM. Businesses can establish the worth of customers by categorizing them, creating customized service plans for various user groups, employing focused marketing tactics, and prioritizing resources toward valuable customers. For airlines, it is crucial to have a strong customer value evaluation system, categorizing customers, and integrating value-focused procedures to be successful in CRM.

The advent of the information age has destined the marketing focus to shift from product-centered to user-centered, and customer relationship management has become a core issue for enterprises. The key issue in customer relationship management is customer classification. By classification, we can distinguish whether customers have value and how high their value is, develop personalized service plans for different categories of users, adopt different marketing plans, and concentrate marketing resources on high-value users. For airlines, it is necessary to establish a reasonable customer value assessment model, group customers, and perform value-based processing.

Algorithm Background
K-Means Clustering
K-Means is an unsupervised learning algorithm used for clustering data into distinct groups. It partitions the data into K clusters, where each data point belongs to the cluster with the nearest mean. The goal is to minimize the within-cluster sum of squares (WCSS).
•	Working Principle: Partitions the dataset into K clusters, with each data point belonging to the cluster with the nearest mean.
•	Advantages: Simple and efficient, particularly with large datasets.
•	Disadvantages: Requires specifying the number of clusters in advance, sensitive to initial placement of centroids.
Decision Tree Classifier
A Decision Tree is a supervised learning algorithm used for both classification and regression tasks. It splits the data into subsets based on the value of input features, creating a tree-like model of decisions. It creates a model that predicts the value of a target variable by learning simple decision rules inferred from the data features. It is intuitive and easy to visualize, making it an excellent choice for understanding customer segments.
•	Working Principle: It splits the dataset into subsets based on the value of input features, creating a tree with decision nodes and leaf nodes. Each decision node represents a test on an attribute, and each branch represents the outcome of the test.
•	Advantages: Easy to understand and interpret, handles both numerical and categorical data, requires little data preprocessing.
•	Disadvantages: Prone to overfitting, especially with deep trees, can be unstable with small variations in data
Support Vector Machine (SVM)
SVM is a supervised learning algorithm used for classification and regression tasks. It finds the hyperplane that best separates the data into different classes. SVM can use different kernels to transform the data and find the optimal hyperplane in higher-dimensional spaces.
•	Working Principle: Find the hyperplane that best separates the data into different classes with the maximum margin. The margin is defined as the distance between the hyperplane and the nearest data points from either class, known as support vectors. The key objective of SVM is to maximize this margin, thereby creating a robust decision boundary.

•	Advantages: Effective in high-dimensional spaces, versatile with different kernel functions.
•	Disadvantages: Computationally intensive, especially with large datasets, sensitive to the choice of kernel and regularization parameters
Briefs about Used Algorithms
1.	K-Means Clustering: Used to segment customers into different value groups.
2.	Decision Tree Classifier: Used to classify customers based on their value metrics.
3.	Support Vector Machine (SVM): Used to classify customers with a high degree of accuracy.
Algorithms Implementation
The following steps were taken to implement the algorithms:
Data Preprocessing
1.	Data Cleaning: Removing records with null values in critical fields.
2.	Feature Selection: Selecting relevant features for analysis.
3.	Metric Calculation: Computing LRFMC (Length, Recency, Frequency, Monetary, and Cost) metrics.
4.	Standardization: Standardizing the data to ensure consistent scaling.
Clustering with K-Means
1.	Determine Optimal Clusters: Use the elbow method to find the optimal number of clusters.
2.	Fit K-Means Model: Apply K-Means clustering on the standardized data.
 
![image](https://github.com/user-attachments/assets/24ce6f8e-15a8-454a-b41f-3f3316212a2f)

6. Train and Evaluate Classifiers
1.	Split Data: Split the data into training and testing sets.
2.	Train SVM and Decision Tree Models: Train models using the training data.
3.	Evaluate Models: Evaluate the models using classification reports and confusion matrices
 
 
![decision_tree](https://github.com/user-attachments/assets/36035de6-85ad-4176-9fb0-2cf1c60ffcfe)

                              
7. Testing and Analysis Results
7.1 K-Means Clustering
•	The optimal number of clusters was determined using the Elbow Method.
•	Clustering resulted in clear segmentation of customers based on their value metrics.
  
Fig 3: Elbow Method for Optimal Number 			    Fig 3: Cluster of Standardized Data
7.2 Decision Tree Classifier
•	Achieved good accuracy in classifying customers into value segments.
•	Classification report indicated precise splits for most classes.
  
      Fig 3: Decision Tree Classification Report 			Fig 3: Prediction graph image

7.3 Support Vector Machine (SVM)
•	Provided high accuracy and clear separation of customer segments.
•	Classification report showed excellent precision, recall, and F1-score for all classes.
  
         Fig 3: SVM Classification Report 			Fig 3: SVM Prediction graph image
8. Algorithm Comparison
•	K-Means Clustering effectively segmented customers, providing a basis for classification.
•	Decision Tree Classifier showed good performance but had slightly lower accuracy compared to SVM.
•	SVM outperformed Decision Tree in terms of precision, recall, and overall accuracy, making it the best algorithm among those tested.

9. Conclusion
The analysis of airline customer value using data mining techniques revealed valuable insights into customer segmentation and classification. The K-Means clustering algorithm provided a solid foundation for segmenting customers, while the Support Vector Machine (SVM) classifier demonstrated superior performance in accurately classifying customers into these segments. Implementing these algorithms can help airlines tailor their marketing strategies and improve customer retention, ultimately enhancing their profitability. Future work can involve exploring more advanced clustering and classification algorithms and incorporating additional features to improve model performance.

Mining Target
Use airline data to segment customers.
Conduct feature analysis on different customer categories and compare the customer value of different categories.
Provide personalized services to customers of different values ​​and formulate corresponding marketing strategies.
Analysis process
The goal is to identify user value. Generally, the most widely used model for identifying customer value is to use three indicators (recent consumption time interval (Recency), consumption frequency (Frequency), and consumption amount (Monetary)) to segment customers and identify high-value users. This is the RFM model.
Just so you know, it is unreasonable to use the amount of consumption (the value of a long-distance economy class user and a short-distance premium class user is different). Therefore, the accumulated mileage M and the average value C of the discount coefficient corresponding to the class of travel are used instead of the amount of consumption.
In addition, the general membership time of this kind of membership-based company also affects the value judgment, so the customer relationship length L is introduced as another indicator.
Finally, the five indicators of this model are customer relationship length L, consumption time interval R, consumption frequency F, flight mileage M, and discount coefficient average C.
Process
We need to conduct an analysis now that we have obtained the required processing indicators. If we use the traditional RFM attribute binning method (based on average value analysis), we can identify it, but there are too many classification result groups, and it is impossible for the company to spend so much targeted marketing costs.
This is a case of cluster analysis, so let's use K-Means cluster analysis.
data collection
Data given.
Data exploration - The main goal is to find missing values ​​and outliers (e.g. the ticket price is 0, the possible reason is exchange or 0% discount)
Data preprocessing
Data cleaning
Obviously, through exploration, we have learned that there are outliers and missing values ​​in the data. Still, the amount of original data is too large and the proportion of such abnormal data is too small, so they can be discarded directly.
Attribute Specification
There are too many data attributes in the original data. According to the required indicators, delete irrelevant, weakly related or redundant attribute columns.
Data Transformation
Attribute construction
Constructing a non-existent indicator
L = LOAD_TIME - FFP_DATE
R = LAST_TO_END
F = FLIGHT_COUNT
M = SEG_KM_SUM
C = AVG_DISCOUNT
Data Standardization
The value ranges of different attributes vary greatly; in theory, the degree of impact should be the same.
Data Mining Modeling
Clustering (based on 5 indicators)
Use K-Means clustering
Characterize each group and sort them (by value)
It is not difficult to see that basically, each category has obvious advantages and disadvantages, and what companies need to do is to modify their marketing plans accordingly.
Subsequent processing
Carry out marketing according to different strategies based on user characteristic ranges.
