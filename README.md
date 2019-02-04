# Small-Business-Loan-project
The files for the Data Incubator project

The goal of my project is to help new entrepreneurs with their main financial decision: Which bank should they ask for the capital to start their business? 

I lived in a small town for the past year and during the weekend I frequently visited the downtown to step into a few local shops and restaurants. I really liked their atmosphere: the friendliness of the owners and employees who, you could see, were proud of being a part of this business. I would like to do my share in promoting these endeavors by giving them a helpful tool in choosing their next loan.

In the United States 99.9% of businesses are considered to be small (500 employees or less), and they employ 58.9 million people, 47.5% of the private workforce. The dataset, collected and curated by the Small Business Administration, has extensive information on all approved small business loans starting from 1991 to the present. It lists which business asked for the money, what type of business is it, which bank gave the money, what was the amount, the term of the loan in months, how many jobs the business supports and more. I ainteractivelso used the NAICS codes found on [Naics Website](https://www.naics.com/business-lists/counts-by-naics-code/?#countsByNAICS) to group the businesses into industry sectors. 

My initial results highlight how the loan amount changes over time and by geographic area. I grouped the data by industry sectors and by the state the business is located to show the relevance of these two factors. The attached map show for various time ranges the average amount per loan in each state. One can check how the loan amount changed over time for every state by switching on and off the various layers of the map (the toggles can be found under the layers icon on the right-hand side). The attached figure shows how the loan amounts varied in time in each sector of the industry. One can see the effect of the 2001 and the 2008 economic crises and the recent surge in investments. There is also a lot of variation that can be seen in the figure, for example in the Public Administration and the Management of Companies and Enterprises sectors. The upper right-hand side has several icons that lets the viewer interact with the figure. One can double click on each legend entry to show only one trendline or use a single click to turn the various trendlines on and off for an easier comparison. 

These graphs illustrate the importance of the knowledge of these factors when deciding on a loan. However, the data is much richer than what these two graphs show. It has information on the outcome of the loan, whether the loan was paid in full, cancelled or charged off. By looking at which sectors and subsectors do these loans belong to and which bank gave the loan we can predict the possible risk. 

I will quantify the variability found in the data for a given set of features. Based on the results of this analysis, I will build a predictive modeling tool to calculate the probability of a loan with a given amount getting approved at a specific time and geographic location. The tool will also give suggestions on the bank the borrower should choose. This will be a helpful tool to any entrepreneur who decides to apply for a loan big or small.  

I expanded the project with a machine learning module that takes these variables into account by calculating a risk factor for the geographic areas and the different business types by using the fraction of loans that will be charged off for the different sectors, i.e. which loans won’t be paid in full. 

Using the amount of loan, the year the loan was approved and the various risk factors as features I ran several machine learning models (Nearest Neighbors, Decision Tree, Random Forest, Neural Net, AdaBoost, Naive Bayes, QDA). At the first step I only used fully paid loans and charged off loans, then I added loans that are ongoing, and lastly, I included loans that were just now approved. The prediction accuracy and the shape of the ROC curves both showed improvement as I included more and more data. See the results at [here] (https://github.com/melivarga/Small-Business-Loan-project/blob/master/ROC_curve_7a.pdf). I made sure that my data is balanced every time, by taking a subset of the original data such that there were the same number of positive and negative examples. I used Python with Pandas, Scikit-learn and Scipy libraries.

I also looked at how the number of loans correlate with population data for every zip code that the data included, which didn’t show very good fit, but when I looked at the number of loans and the number of businesses for a given state I found a very good linear relationship with and R2 of 0.982. See figure [here] (https://github.com/melivarga/Small-Business-Loan-project/blob/master/LoanCount_vs_NoBusinesses.pdf). For these analyses I collected data from the web using API. 

In the future I would like to use new and improved features and implement a neural network using Tensorflow to predict all types of the loans with a higher accuracy and expand the regression analysis by taking into account the size of the company and various other features. 
