# Project 
    Code: 10281
## Employee Performance Analysis
### INX Future Inc.
### Project Summary
   INX Future Inc, is one of the leading data analytics and automation solutions provider with over 15 years of global business presence. INX is consistently rated as top 20 best employers past 5 years. In recent years, the employee performance indexes are not healthy and this has become a growing concern among the top management.CEO, Mr. Brain, knows the issues but concerned to take any actions in penalizing non-performing employees as this would affect the employee morale of all the employees in general and may further reduce the performance. The CEO Mr. Brain, decided to initiate a data science project, which analyzes the current employee data and find the core underlying causes of the performance issues. He also expects a clear indicators of non-performing employees, so that any penalization of non-performing employee, if required, may not significantly affect other employee morals.

The following requirements that are expected from this project:

1. Department wise performances.
2. Top 3 Important Factors effecting employee performance.
3. A trained model which can predict the employee performance based on factors as inputs.
4. Recommendations to improve the employee performance based on insights from analysis.

### 1. Requirement
   The data obtained from the IABAC for this project where the collected source is IABAC. The data is based on INX Future Inc, (referred as INX ). The data is not from the real organization. The whole project was done in Jupiter notebook platform using python.

### 2. Analysis
   The data obatained is 1200X28 shape which contains both numerical and categorical columns. The predictors are both ordinal and nominal. Target is a ordinal catergorical feature.
#### (i) Analysis by the distribution of the data
Minimum age of employee is 18 and maximum is 60 50% of the mployee are between 30 - 43, max people are of age 34.
Distance from home is measures in units ranging from 1 - 30 50% of people distance between 1 - 7 units.
Number 50% of people have worked for atleast two companies.
Most of the employee hourly rate is between 48 - 85.Features like EmpEnvironmentSatisfaction, EmpLastSalaryHikePercent, EmpWorkLifeBalance has high positive correlation wih the target.
EmpEducationLevel, NumCompaniesWorked has moderate positive correlation with the target. 
#### (ii ) Analysis by the visualization
    
   #### Department wise performances :
   
   1. More number of employees in sales department are having poor performances comparatively, sales has the quite good number of average performers too.
   2. Human Resources have more number of rating 2 than the number of 4 ratings but the moderates performers (rating 3) is quite high.
   3. Highest average performance(rating 3) is in development team with quite high number of good performances(rating 4) and very few low poor performances.
   4. There are average performers and few best performers in data science with negligible worst performances.
   5. Research and development has the second most worst performances with quite few best performances and huge moderate performances(rating 3)
   6. Finance has very few best(rating 4), more number of moderate performances, and noctiable amount of low performances.
   
#### Top three factors affecting the performance :
   Feature immpotance using  gradient boosting classifier to obtain the level of features at which they are affecting the target.
   1. Employment Environment Satisfaction
   2. Employee Salary Hike Percentage
   3. Years Since the last Promotion
   
   These features also showed good correlation with the target too.
   
Detailed analysis on how these features are influencing the performances in each derparment are explained in  'visualize.ipynb' .

### 3. Summary
   In order to train the model to predict the performances few transformations of the data is needed to be done to make the machine learning algorithm (model) learn the data well. The preprocessing techniques like label encoding was done to convert the non-numeric categorical data into numeric ones. Feature importance was done in the visualization us gradient boosting classifier to obtain the top 16 important features to the make the model predict well(with all fetures the performance wa low).The data was split into train and test data before further processing the data to avoid data leakage. The data contianed three classes in the target feature to classify but the number of data in each classes were inequal. This could create bias in the model. In order to decrease the bias to some extend and develop a more generalized model synthetic data was created using smoting technique. Traditional models like logistic regression, random forest an ensemble techniques which use a collection of decision tree to find the better predictions were used using sklearn library for. Then advanced algorithms like XG boost which is an optimized distributed gradient boosting library designed to be highly efficient, flexible and portable. It implements machine learning algorithms under the Gradient Boosting framework  and cat boost which is again a gradient boosting on decision trees were also used to see the predictions.
    Apparently random forest won the race.
    

   ### Model with the results(accuracy)

1. Logistic Regression  -  73.33 %
2. Random forest classifier - 93 %
3. XG Boost  - 90.66 %
4. Cat Boost - 92.33 %

The result were mainly focused predicting the class 2 and 3 precisely (to penalize or take further actions) and to avoid misclassifiaction of class 4 performers to be wrongly classified as 2 or 3 (especially 2) to avoid loosing best performing employees from the company.


### Recommendations 
   The factors that are mostly affecting the perfromance are Employee satisfactions, Hikes, Promotions, Training times, distance from the office to home.
      
   So a timely hikes in salary (20% hikes performance boosts) and promotions can be done because these accounts as the appreciation for the works. Training times atleast 2 times would lead in good perfomance also transport facilities play some part in the employees performance. With these factors collectively increases the top most important factor Employee environment satisfaction (employee satisfaction) and would get the company back into top 20 rating as it was 5 yrs ago.
