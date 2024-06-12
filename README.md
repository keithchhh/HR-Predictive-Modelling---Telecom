Conclusions
Objective 1: Model the probability of attrition amongst employees

XGBoost shows the highest macro scores for precision, recall and f-1 at 97-98%, this is followed by random forest (94-96%), decision tree (78-87%) and Logistic Regression (65-73%)

The XGBoost model has 6 false positives and 13 false negatives in the test size of 30%, outperforming the other models.


# Model macro scores for all models tested
data = {
    'Model': ['Logistic Regression', 'Decision Tree', 'Random Forest', 'XGBoost'],
    'Precision': [0.65, 0.78, 0.96, 0.98],
    'Recall': [0.73, 0.87, 0.94, 0.97],
    'F-1': [0.66, 0.81, 0.95, 0.97]
}

df = pd.DataFrame(data)
df_sorted = df.sort_values(by='Precision', ascending=False)
df_sorted.reset_index(drop=True, inplace=True)
print(df_sorted)
     
                 Model  Precision  Recall   F-1
0              XGBoost       0.98    0.97  0.97
1        Random Forest       0.96    0.94  0.95
2        Decision Tree       0.78    0.87  0.81
3  Logistic Regression       0.65    0.73  0.66
Objective 2: Develop strategies to reduce the current attrition rate.

By aggregating the decision tree, random forest, and XGBoost model's infleuncing factors at a weight of 0.15, 0.25, and 0.6, a more holistic view of what affects an employee's decision to leave the company can be made.
These factors are:

Hours Worked - Overall, employees that work longer hours are more likely to leave the company. This may be because of inadequate training or improper skill fit hiring, or unequal work distribution. This may lead to employee having to work longer hours to complete their work. Moreover, employees may be encouraged to work longer to get higher performance rating. This may lead to overwork and burnout.
Set policies to address overwork amongst employees and encourage employees to finish work within working hours (below 8). In the case that the workload exceeds working hours, managers must identify areas of work thta can be further automated or hire additional staff.
Moreover, managers should also ensure equal work distribution and proper remuneration for the extended hours (see point 5).
Training plans need to be examined by the company in teaching employees the proper skills to efficiently finish their work. Training does not seem to significantly reduce the number of hours worked, suggesting either 1) the training is not adequate in addressing employee workload, or 2) the number of hours worked is not related to training and may be related to unequal workload.
Employees that work more hours generally have a higher performance rating, managers must examine their approach to workplace evaluation and address overwork as well as reduce workplace competition.
Age - younger age groups are more likely to leave the company, especially the youngest age groups such as 18-25 have an attrition rate of around 34%, whilst 25-35 have an above average attrition rate of 19%. This is possibly due to a lack of career growth opportunities or skill development opportunities.
To address this, the telecommunications company should conduct a more comprehensive identification of career goals of younger individuals who join the company, orgnaize one on ones with younger employees to further understand what specific programs to develop to meet their goals.
This is usually related to training and development opportunities to gain experience or career progression, thus the telecommunication company may consider implementing a more robust learning and development program as well as career rotations and a career path to ensure younger employees are more inclined to stay.
Human Resources Department - There is a high amount of turnover in the HR department (30%), compared to the other departments (~15%). This is not related to the number of hours worked and employees and managers ahve similar sentiment compared to other departments. More has to be done to ensure HR employees stay.
To address high HR department turnover, the company must launch an investigation into the key factors contributing to high turnover within the department. This seems to be related to the fact that there is high turnover for younger employees (71%) and all age levels. For younger employees, perhaps more training and development opportunities or career progression is needed.
This may be related to the lower monthly income that HR department receives (see point 5).
Marital Status - Employees that are single are more likely to leave the company (25%), compared to those that are married or divorced (15%). This is directly linked to their age, where younger people tend to be single and have less responsibilities or obligation to the others.
Single employees are likely to have a different set of priorities than those that are married or divorced, this includes expanding their network or connections. The company may conduct further investigation into their objectives, as well as organize events that meet their needs.
Monthly Income - Despite workers working more hours, the compensation of the employees that leave the company are on average less than those who stay. This can be related back to the different departments, where employees that left received on average 5000 less than those who stayed in the company. Considering they are overworked, a proper compensation plan must be awarded for those who work longer hours.
Develop a compensation plan for employees that choose to work longer hours, as the employees that leave the company on average work longer but earn a lower monthly income.
Identify the industry standard level of compensation for departments, especially HR (where the mean monthly income of employee attrition is 5000, which may be lower than industry standard and encourage them to leave the company.
Objective 3: Develop recommendations to improve the efficiency of the data collection/analysis process

Data Collection

Automatically join files based on the employeeid column in one large file to increase efficiency of data collection/analysis.
Set automatic reminders for employees to fill in any missing values in their surveys or other missing data points. This can improve accuracy of the model to not base off mean values.
Include average attrition rates for similar companies and departments in the industry to allow good comparison.
Data Analysis

Consolidate the variables as there are too many variables that may affect the accuracy or validity of the predictive models and lead to overfitting due to the model being too complex. This may be why the XGBoost model has a 97-98% performance in the macro scores of f-1, precision and recall.
Automatically calculate variables such as hours worked, days off and other predictive variables that are included in the model.
Create a dashboard visualization that tracks key variables to assist analysis over time, assuming this is not a one off project but to track changes after implementing recommendations, a dashboard visualization can assist the company in quickly understanding areas of improvement.
