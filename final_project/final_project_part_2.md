# Final Project Write-up

### Project Problem and Hypothesis

<b>Project:</b> <u>[Santander Customer Satisfaction (Kaggle Competition)](https://www.kaggle.com/c/santander-customer-satisfaction)</u>

<b>Problem:</b>
From frontline support teams to C-suites, customer satisfaction is a key measure of success. Unhappy customers don't stick around. What's more, unhappy customers rarely voice their dissatisfaction before leaving.

Santander Bank is asking to help them identify dissatisfied customers early in their relationship. Doing so would allow Santander to take proactive steps to improve a customer's happiness before it's too late.

The competition provides dataset with hundreds of anonymized features to predict if a customer is satisfied or dissatisfied with their banking experience.

It is supervised learning binary classification task. My goal is to learn training data and predict the categorical class labels of new instances based on past observations. Other words, machine learning algorithm should learn a set of rules in order to distinguish between two possible classes: satisfied customer or unsatisfied customer.

A successful prediction will help Santander Bank to keep their clients and make profit.

<b>Null Hypothesis:</b>
Each customer in the test dataset is an unsatisfied customer.


### Datasets

Train and test datasets are provided by Kaggle. An anonymized datasets contain large number of numeric variables. "ID" column shows the customer’s identifier. The "TARGET" column is the variable to predict. It equals 1 for unsatisfied customer and 0 for satisfied customer.

<u>File descriptions:</u>
<ul>
    <li>train.csv - the training set including the target (76020 rows x 371 columns)</li>
    <li>test.csv - the test set without the target (75818 rows x 370 columns)</li>
</ul>


### Domain knowledge

According to [American Customer Satisfaction Index (ACSI)](http://www.theacsi.org/industries/finance-and-insurance/bank) bank customer experience benchmarks include variety of financial services, adding or making changes to accounts, interest rate competitiveness, branch number and location, understanding account information, ATM number and location, staff courtesy, financial transaction speed, website. Each year, the ACSI interviews hundreds of customers about recent experiences with the checking, savings, or loan services offered by their banks. But in this particular research I have anonymized dataset with unknown information. It means that it is almost impossible to provide the accurate reasons of customer satisfaction in plain English.
 

### Project Concerns
<b>Assumptions:</b>
<ul>
  <li>I suppose that customers who have certain amount of transactions throughout all columns are dissatisfied.</li>
  <li>I suppose that customers who have particular transactions are dissatisfied.</li>
</ul>  

<b>Open Questions and Concerns:</b>

I will need to understand the features and probably do feature engineering to improve my model. 

<ol>
    <li>There are 370 columns in dataset. How to select right columns? Should I use some common strategy to handle them?</li>
    <li>I'd like to run scatter matrix, seaborn heatmap or pairplot to see correlations. How to do it more efficiently? Should I run it 
for all table at once or it makes sense to split it by 10, 15 ... columns?</li>
    <li>There are a lot of zeros in dataset. Does it mean that data is unavailable or balance is zero? Should I do something with it?</li>
    <li>Several columns have categorical variables, for example, num_var4. Should I create dummy variables for them?</li>
    <li>How to handle data normalization? For example, if you look at <a href="./final_project/final_project_part_2.ipynb">data</a> it looks like last column var38 contains account balance. Should I research each column on normalization?</li>
    <li>Is there a way to use feature engineering if you don't know the meaning of each column?</li>
    <li>There are various paradigms that are used for learning binary classifiers which include: 
        <ul>
          <li><a href="http://scikit-learn.org/stable/modules/svm.html">Support Vector Machines (SVM)</a></li>
          <li><a href="http://scikit-learn.org/stable/modules/naive_bayes.html">Naive Bayes</a></li>
          <li><a href="http://scikit-learn.org/stable/modules/tree.html">Decision tree</a></li>
          <li><a href="http://scikit-learn.org/stable/modules/ensemble.html">Random Forest</a></li>
        </ul>
    <br>Also I probably have to use <a href="http://scikit-learn.org/stable/modules/feature_selection.html">feature selection</a> and dimensionality reduction in order to remove noise and reduce the size of the dataset.
    <br>Which algorithm I should use to get more accurate result?</li>
</ol>

### Outcomes
Output file should contain two columns – "ID" and "TARGET". 
"ID" column should show the customer’s identifier from test dataset and "TARGET" column should show prediction if customer is dissatisfied (1) or satisfied (0).

There are 2,760 teams that participate this competition. The best AUC score is 0.84 (I suppose it might be overfitting here) and the worst AUC score is 0.35. The goal is to find the best score using different algorithms but try not to overfit the model.

It is an attractive competition to get involved in, because the data is pretty clean and I can spend my time learning about feature engineering and different prediction algorithms.
