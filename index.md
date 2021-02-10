# Stack Overflow Data Base Respondents' Job Satisfaction Questions - 2017 Survey.

The dataset has more than 50,000 observations and 154 variables. On this data base I was interested in asking myself the following questions: 

Question 1: How does job satisfaction behave?

Question 2: If a person has high career satisfaction (CareerSatisfaction), will he/she also have high job satisfaction (JobSatisfaction)?

Question 3: What qualitative and quantitative variables influence an employee to have high JobSatisfaction?


#### Base df (Public survey results)
![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/1.PNG)

#### Descriptive statistics Quantitative Variables Database df

Next we find that of the 145 variables, 6 are quantitative since the "Respondent" column is an identifier column. It is evident that the variable "ExpectedSalary" contains very little data (2,566) only 5% of the people answered that question.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/2.PNG)


## Question 1: How does job satisfaction behave?

A summary of descriptive statistics was calculated for the _JobSatisfaction_ variable, where it can be seen that on average job satisfaction is 6.9, which means that most respondents have good job satisfaction. It is also evident that the 1st percentile (25%) is 6, therefore 75% of the respondents have a job satisfaction above 6, which is acceptable, as can be seen in the following table, bar chart and box plot.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/3.PNG)

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/4.PNG)

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/5.PNG)

The following tables compare job satisfaction with employee status, company size and country. From this we conclude that the employees with the lowest job satisfaction are those with full-time contracts.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/6.PNG)

It is also evident that the employees with the highest job satisfaction are those who work for companies with 10 to fewer employees, followed by companies with 10 to 19 employees; from here it is concluded that those with the highest job satisfaction are employees whose companies have few employees.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/7.PNG)

Given the following tables we conclude that the countries with the lowest job satisfaction are Saint Lucia, Fiji and American Samoa, on the contrary the countries with the highest job satisfaction are: Macau, Libya and Angola.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/8.PNG)

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/9.PNG)

## Question 2: If a person has high CareerSatisfaction, will he/she also have high JobSatisfaction?

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/10.PNG)

The correlation diagram above shows that among the quantitative variables, the highest linear relationship is found between the JobSatisfaction and CareerSatisfaction variables, with a correlation of 0.65. Having this correlation indicates that there are indications that the higher the JobSatisfaction, the higher the JobSatisfaction. Next we will perform a simple linear model to verify if this variable has an impact and what is its impact?

#### Definición base de datos para la realización del modelo.

Given that the model is going to be made only with the JobSatisfaction and _CareerSatisfaction_ variables, make a subset to the base with these two variables.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/11.PNG)

Since the database contains null values, we proceed to eliminate the rows with null values, leaving a total of 40,352 records for the model.

#### Modelo lineal Simple

After performing the simple linear regression we observe that the R2 is equal to 0.4170 which indicates that the variable 'CareerSatisfaction' explains a part of the variable 'JobSatisfaction', however after testing with more variables in alternate exercises it fails to increase its r2, therefore we review the Prob (F-statistic) and P_value statistics of the variable 'CareerSatisfaction', to determine if it is significant.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/12.PNG)

It is evident that the probability of the F statistic, Prob(F statistic)=0.00 is less than 0.05% , with a level of 95% we can reject the null hypothesis (Ho), that is to say that the model is explanatory, therefore the variable 'CareerSatisfaction' of the model has an effect on the response variable 'CareerSatisfaction' and we also observe that the p_value (P> t) of the variable 'CareerSatisfaction' is 0.000, less than 0.05%, that is to say that it is significant for the model.

Therefore, we conclude that the degree of satisfaction with a career has an influence on job satisfaction, but it is not enough to explain job satisfaction; therefore, there must be other variables that also contribute to higher job satisfaction.


## Question 3: What qualitative and quantitative variables influence an employee to have high job satisfaction (JobSatisfaction)?

Since the database contains more than 140 qualitative variables, we selected the qualitative variables that are most related to working conditions such as: 'EmploymentStatus'_, _'CompanySize' and _'SeriousWork'_, this selection of variables is made from the researcher's point of view.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/13.PNG)

Since the database contains null values, we proceed to eliminate the rows with null values, leaving us with a database of 22498 records to model.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/14.PNG)

### Multiple linear model:

In order to analyze qualitative variables in the multiple linear regression model, it is necessary to convert each category of each variable into 1 column respectively, this process is known as "one-hot encoding".

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/15.PNG)

After obtaining the base, all the variables are introduced into the model in order to determine which are the most relevant.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/16.PNG)

After running the model, we found that there are multicollinearity problems, since all the columns were entered into the model. Therefore, several interactions were performed selecting different variables and the model presented below is the best model that iterated with an R2 equal to 89.3% and indicates that the 'EmploymentStatus' variable is significant for the model, i.e. the employee's status positively influences the worker's satisfaction.

![](https://raw.githubusercontent.com/gustavovenegas2010/Proyecto-1/main/Imagenes/17.PNG)

#### After asking the question: _Which other qualitative variables are significant and influence an employee's job satisfaction?_, find out by replicating this code with other variables.

