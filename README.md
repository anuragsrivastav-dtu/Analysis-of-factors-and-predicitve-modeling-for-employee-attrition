# MOTIVATION AND OBJECTIVE OF THE PROJECT  
I am a data enthusiast and love to play with data; the process of deriving insights and conclusions from data is what excites and drives me. The ability to extract stories from raw information is not only a source of excitement for me but also a driving force in my passion for exploring the vast and dynamic world of data. Along with this, I am deeply fascinated by the complex mechanism of human behavior in various social and personal settings, and it is amusing to observe various trends and patterns that shape the decision and behavior of people. This analysis is of very practical utility for businesses since it allows them to gain a deeper insight for developing relevant strategies and policies for long-term success.  

**This project is made with the objective to find key metrics that lead to employee quitting the job at an organization and provide relevant strategies for increasing employee retention in the business. A robust machine learning model was developed, after proper modeling of the data, that can precisely predict the attrition probability for an employee, based upon which relevant strategies can be built for addressing it. This project is a very practical and efficient solution to a real business problem that exists in the industry and has allowed me to understand how data analysis can directly impact business operations. The in-depth analysis of metrics and high accuracy of the model portrays my firm understanding of core data analysis and statistical concepts and my strong ability to use relevant tools for delivering impactful solutions to real-world problems in the industry**
# Data Acquisition
I used IBM HR Analytics Employee Attrition & Performance data from Kaggle, which is created by IBM data scientists. Dataset is in the open source website and can be reached from this link. It has 1470 rows x 35 columns and contains numeric and categorical data types in columns. I loaded the dataset from this link in csv format and read it in the Jupyter notebook after importing necessary libraries.  

Data Specification: The dataset has 1470 rows and 35 columns. Rows are observations from each employee and columns are from different features which are obtained in order to explain the employee attrition. The features data types consist of 27 integers and 8 objects.

# Data cleaning
 I searched for missing values in every features of dataset, all features look like having 1470 non-null entries. However, missing values can be encoded in a number of different ways, such as by zeroes, or questions marks. For that reason, I checked both missing values and duplicate values in the dataset. Luckily, it was okay to continue to next step. I observed 5 random sample records in the dataset to grasp the general intuition about whole picture. Besides that, I explored the statistical attributes of each features such as their mean, standard deviation, interquartile values in order to detect outliers. This research also gave me a general impression about unique and top values for each attribute in addition to their frequencies in the dataset. I made double checks on some of features in order to make sure that everything is good to go. Those results were also okay. I inspected the useless features in order to drop in the dataset. “Over 18”, ”StandardHours”, and “EmployeeCount” had only one unique value for each observation and that did not impact or change anything in the data. For that reason, I dropped those three useless columns. To be able to use effectively in the further steps, I reassigned the response variable (Attrition) which had “Yes” and “No” values previously. They were assigned to 1 and 0 respectively. After that, I moved the response variable to the last column place. The dataset has 8 object types which are 'BusinessTravel', 'Department', 'EducationField', 'Gender', 'JobRole', 'MaritalStatus', 'OverTime'. To be able have more memory usage and 3 become fast, I changed object type to category type in the dataset. At first memory usage was 402.0+ KB, and after changing the data types, it became 298.3 KB  

 # Exploratory Data Analysis 
 We have 32 features consisting of both categorical as well as the numerical features. Response variable is 'Attrition' of the employees which can 1 and 0 (representing 'Yes' and 'No' respectively). This is what we will predict. Now, I will try to analyze visually the trends in how and why employees are quitting their jobs. For that, I will deep dive into the details about features and their relationships between each other  

   
**FEATURES:**

**AGE :**  
  <div align=”center”>![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/442cbfb4-da0a-4081-a67f-a03c7f438f94)</div>  

In 18-21 age group, young employees are more likely to leave the company. Their attrition proportion to their age group is approximately 53.7% (22 out of 41) and that makes up 9% of all attrition (22 out of 237). If we evaluate overall attrition number in the company, 26-35 age group's attrition number is the highest comparing to other age groups. In this age group, we have 19.1 % of employee attrition(116 out 606). That makes up approximately 49% of all attrition in the company (116 out of 237).35-60 age group generally prefers to secure their job in the same company.  
Business Travel:  
 
​  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/e7d61c1e-9f0b-4882-9662-838238a92652)  

In the company, most of the employee travel rarely or don't travel according to their job description. That group compose the 81.1% of entire company(1193). The rest of the company employees which is 19.9% of them must travel frequently (277 out of 1470). 
The highest attrition number with 156 belongs to the employees who travels rarely. That is approximately 15% of employees in that group (156 out of 1043). But when you put this number overall attrition, it makes up 65.8% of all attrition in the company(156 out of 237)
if we look at the attrition percentage of relevant travel group, the employees who are traveling frequently are in the danger zone. Because they have the highest attrition proportion, which is 24.9%, in their individual travel group(69 out of 277). That group's attrition rate composes of the 29.1% of overall attrition in the company (69 out of 237).  

**Department:**    
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/b8a4adc1-e665-4454-89f0-ad4db8a86b05)  

There are three departments in the company. Research & Development Department has the most attrition number in the company. 13.8% of Research & Development Department employee left the organization. In numbers, it is equal to 133, which makes us the 56.1% of all attrition in the company. Actually, this attrition is a big number for company, but compared with other departments, Research & Development Department has the lowest attrition rate in itself as an individual department. Sales Department has mostly been affected by the attrition. Because 20.6% of its employees left the organization. This is the highest number compared to the other two departments. That attrition makes up 38.8% of the attrition in the company (92 out of 237). Human Resources Department follows the Sales Department in terms of being affected by attrition itself. 19% of that department employee left the company. But this is not that huge number in terms of whole attrition in company. Human Resources Department employee attrition makes up 5% of all attrition in the company (12 out of 237).  

**Distance From Home:**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/e7d31a14-10ec-4169-a5e5-38b4af56f34d)  

Employees whose homes are 1-3 miles far away from the company compose approximately 1/3 of the whole company employee and their attrition rate is 28.7% of all company (68 out of 237). Also, employees whose homes are 10+ miles far away from the company compose approximately the other 1/3 of the whole company employee and their attrition rate is 39.2% of all company (93 out of 237).
Attrition rate within its own distance group seems to increase as the distance from home increases.  

**EDUCATION :**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/a021f99d-87e5-4d41-a32c-a08c2a5ebe5a)  
Employees who have bachelor’s degree have the most attrition number (99 employees) in the company. That makes up 41.8% of all attrition in the company. Employees who have Ph.D. degree composes the least attrition number in the company. Employees who have the master, college, and below college degrees are follower of employees who have bachelor’s degrees in terms of the attrition number in the company respectively.  

**EDUCATIONAL FIELD:**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/ab30c181-4a87-4214-b2da-1701fe7f6d28)  

Employees who have Life Science education level have the most attrition number which makes up the 37.5% of all attrition (89 out of 237). But that composes only 14.7% of attrition within Life Sciences field. Medical education level have the second highest attrition number which makes up the 13.57% of all attrition (63 out of 237). But that composes only 14.7% of attrition within Life Sciences field. Besides that, Human Resources, Technical Degree, and Marketing fields are mostly affected by the attrition respectively. Their approximately 22-26% employees left the company.  
**ENVIRONMENT SATISFACTION :**   
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/c656bc39-58b0-4848-b877-e0a4aeab1e32)    
As it may be expected, there is a high attrition rate in the low satisfaction environment. That composes the 30.4 % of the whole company's attrition. Shockingly, in the high and very high satisfaction environment, there are still 13.7 % of the these each group's employees leave the company. That attrition composes of the 51.5 % of the whole company's attrition. This result might tell us that environment satisfaction is not the one of the main reasons for attrition in the company.    

**GENDER :**  
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/6587b676-dd2f-4c16-a38f-0e8811d4fdb4)  
Male employees are more likely to leave the company than female employees.  

**JOB SATISFACTION :**  
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/d6d5d291-c80c-4721-93f1-86ebd2d859f2)  
I found quite interesting insight for job satisfaction, which may be quite counter-intuitive:In high job satisfaction, surprisingly employees leave the company most and their attrition composes 30.8% of company's attrition. From this picture, I assume that job satisfaction should not be the main reason for employees to leave the company. As it may be expected, in low job satisfaction, employees leave the company more than other groups except high satisfaction. They compose 27.8% of all attrition in the company.

**MONTHLY INCOME :**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/2d947321-0ba1-48ab-b65c-94c80281c545)  

2000-3000 dollars monthly income level, there is a high attrition and it compose the 40% of attrition in the company.

1000-2000 dollars monthly income level, there is a high attrition in its own income group level, which is 54.5%.

As the monthly income increase, it is observed that there is a decrease in attrition. But, in 9000-11000 dollars monthly income level, there is a rise in attrition of its own monthly income group level.  
**NUMBER OF COMPANIES WORKED :**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/5a05bcac-00a9-4262-af94-51daccb64d61)  
If employees have one company experience before current company, they are more likely to leave the company. They have the highest attrition number and compose of 41.3% all attrition in the company. Besides, if employees don't have any experience in other company, they have the second most attrition number.

Also, employees, who has more experience such as working in 5,6,7, and 9 companies before the current company, have the highest attrition in their individual experienced group.  

**Over time :**  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/3f27acc8-f4c6-42e5-9e01-c96f83f67759)  
28.3% of employees have the over time work in the company and they have higher attrition number than employees who don't have. There is not a significant difference between these two groups' attrition number. But if you compare individually both groups, over time employees are much more likely to leave the company.  
**PERCENT SALARY HIKE :** 
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/1334d22d-a317-4f4e-8f65-ded6970946bf)  
As it may be expected, the higher percent salary hike is, the more employees are likely and willingly to stay in the current company. The employees who have the highest percent salary hikes are more likely to leave the company. The reason for that might be due to the fact that they are more qualified and have the chance to find better position in other companies or due to the retirement.  
**WORK LIFE BALANCE:**  
​  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/53b0f3b6-08ab-4795-8ae5-da4b69310a81)  
In general, work life balance is satisfactorily good throughout the company. But we have the highest attrition number and percentage throughout the company.Besides, bad work life balance group has highest attrition percentage in its individual group.  
**YEARS AT COMPANY :**  
  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/8ba15e7f-e4a7-4b83-a98d-dc99f6357bae)  
Employees who have one year or less working experience in the company has the highest attrition percentage in its individual experience group (34.9% of attrition in the relevant group). Besides that, highest attrition number, which is 87 employees, is in the 2-5 years working experience at the company and that composes of the 36.7 % of all attrition in the company.  
# CORRELATION MATRIX :
In this section, i have depicted the correlation matrix obtained for our case, which is one of the statistical analysis concept, used to determine how each variables correlate with the other variables. It helps in the identification of patterns and dependencies within a dataset giving a much more comprehensive understanding of combined effect of the variables.  

  ![download](https://github.com/anuragsrivastav-dtu/Analysis-of-factors-for-employee-attrition/assets/140643875/699a682a-8a8e-4249-86d1-57984ea3e519)  
Based on the fact which is given strength of correlation chart, we can identify the features which have strong, moderate, weak and zero correlations between each other. I will just outline the strong and moderate correlations here.  
**Features which have strong correlations:**  
- Percent Salary Hike and Performance Rating,

- Total Working Years, Monthly Income and Job Level,

- Years at Company, Years with Current Manager, and Years in Current Role,



**Features which have moderate correlations:**

- Age has moderate correlation with Total Working Years, Monthly Income, and Job Level,

- Job Level has moderate correlation with Years at Company and Age,

- Total Working Years has moderate correlation with Years with Current Manager, Years Since Last Promotion, Years in Current Role, Years at Company, and Age,

- Years at Company has moderate correlation with Years Since Last Promotion, Total Working Years, Monthly Income, Job Level,

- Years in Current Role has moderate correlation with Years Since Last Promotion, Total Working Years,

- Years Since Last Promotion has moderate correlation with Years with Current Manager, Years in Current Role, Years at Company, Total Working Years,

- Years with Current Manager has moderate correlation with Years Since Last Promotion, Total Working Years.



# SUMMARIZING THE KEY INSIGHTS GENERATED :

- There are 1470 employees in the company and 16% of them left the company. We have some data about employees       to examine the attrition reasons. To sum our exploratory data analysis : 

- Young employees (18-25 years old) compose the 8.4% of the company and they are more likely to leave the company than other age groups. As the employees get older, their attrition percentages drop.

- Employees who travel rarely or don't travel according to their job description compose the 81.1% of entire company. 18.8% of the employees travels frequently and they have the highest attrition percentage(25%).

- 30.3% of employees work in the Sales department and they have the highest attrition percentage (20.6%). Human Resources employees who compose the 4.3% of company, are the second highest attrition percentage(19%). Research and Development Department has 65.4% employee in the company and they have the lowest attrition percentage(13.8%).

- As the distance between company and employees’ homes increases, the attrition percentage increases.

- 11.6% of employees has below college degree and highest attrition percentage(18.2%). Other attrition percentages according to education levels: 39% of employees has the bachelor’s degree and 17.3% attrition. 19.2% of employees has the college degree and 15.6% attrition. 27.1% of employees has the master’s degree and 14.6% attrition. 3.3% of employees has the doctorate degree and 10.4% attrition.

- According to the education field, 1.8% of employees has Human Resources education field and highest attrition(25.9%). 8.9% employees have Technical degree education field and 24.2% attrition. 10.8% of employees has Marketing education field and 22% attrition. Life Sciences, Medical and other education fields are affected respectively.

- 61.2% of employees has environment satisfaction at very high/high level in the company. 19.3% of employees has low environment satisfaction and 25.3% attrition.

- Male employees(60% of company) are more likely to leave the company than female employees.

- 68.8% of employees has high/very high job involvement in the company. As the job involvement increases, the attrition percentage decreases respectively.

- 37% of employees has job level-1 and 26.3% attrition. Job level-3(14.8% of the company) and job level-2(36.3% of the company) are affected mostly by %14.7 and 9.7% attrition after job level-1 respectively.

- 5.6% of employees works as Sales Representative and they have the highest attrition(39.8%). Laboratory Technician (17.6% of employees) and Human Resources (3.5% of employees) job role follows the Sales Representative attrition percentage by 23.9% and 23.07% respectively. Besides those job roles, Sale Executive (22.8% of the employees have 17.5% attrition) and Research Scientist (19.9% of employees have 16.1% attrition) have the higher attrition percentage than others.

- 61.3% of employees has high/very high job satisfaction in the company. 19.7% of employees have low job satisfaction and highest attrition percentage(22.8%). As the job satisfaction increase, attrition percentage decreases. Medium(19% of employees) and high(30% of employees) job satisfaction has approximately same attrition percentage(16.5%).

- 32% of employees are single and has the highest attrition percentage(25.5%).

- 26.9% of employees have 1000-3000 dollars monthly income and highest attrition percentage(47.7%). Other monthly income employees have been affected by attrition in the same percentage level except 9000-11000 dollars monthly income level. That group is 5.6% of employees and has 18.6% attrition.

- 35.4% of employees have one company experience before current company, and they are more likely to leave the company(18.8%). 21% of employees worked in 5 and more companies before this company and have 21.8% attrition. 28.3% of employees have over time and 30.5% attrition in the company while rest of the employees have only 10.4% attrition.

- The higher percent salary hike is, the more employees are likely and willingly to stay in the current company.

- Performance rating has two category such as 3 and 4. 84.6% of employees are in the performance rating 3 group and 16.08 attrition. The rest of the employees are in performance rating 4 group and their attrition percentage(%16.37) is a little bit higher than previous group.

- 18.8% of employees have low relationship satisfaction and highest attrition percentage(20.7%). The rest of the employees’ attrition percentage is at 15% band level.

- 43% of employees has zero stock option level and highest attrition percentage(24.4%). There is a sharp decrease in attrition percentage until stock option level-3. %5.7 of employees has stock option level-3 and 17.4% attrition.

- As the total working years increases, the attrition percentage decreases in the relevant experience groups.

- 70.6% of employees have 2-3 times training in the previous year and have 17.9% and 14.1% attrition respectively. 3.7% of employees does not have training times in the previous year and has the highest attrition percentage(27.8%). 8.3% of employees have 4 times training last year and have 21.1% attrition. The rest of the employees’ attrition percentage is around between 9% and 12%. 84.2% of employees have good or better work life balance, and 16.7% and 14.2% attrition respectively. 5.4% of employees have bad work life balance and the highest attrition percentage(31.3%). As the years at company and current role increase, attrition percentage decreases in the company.

- 39.5% of employees leaves the company before fulfilling one year since their last promotion. 24.3% of employees fulfilling one year since their last promotion has the 13.7 attrition percentage. 7 years since last promotion employee group (5.2%) has the highest attrition(21.1%) in its individual group.

- Most of the employee(17.9%) quit the company before completing their first year with their current manager(32.3% attrition). Other group who leaves the company most is the ones who work two years with current manager(23.4% of employees with 14.5% attrition).

I also checked the 'Employee Number', 'Daily Rate', 'Hourly Rate' and 'Monthly Rate' features as I did the in previous features of dataset. But there is nothing significant to comment or visualize about these features.

​

# RECOMMENDATIONS FOR THE COMPANY:

- Based upon the insights I would give the followingrec

- 28.3% of employees have over time work in the company and 30.5% of those employees leave the company. As it is also reflected in the model, employees working overtime are significantly more likely to resign. Therefore, the company should understand the reason why they are working overtime. Is it for too high workload or are employees' qualifications not enough to complete the scheduled tasks on time? Maybe there might be some other reasons behind that. Our recommendation will be to understand the reason(s) for overtime with detail research and take appropriate measures to reduce the factors behind this attrition factor.

- 18.8% of the employees travels frequently, and they have the highest attrition percentage(25%). The company should question what makes traveling a burden on their employees. The company should balance the travel status and if necessary, there might be some adjustments on the job description in terms of traveling. The company may use some extra incentives to motivate their employees who are supposed to travel.

- 21% of employees worked in 5 and more companies before this company and have 21.8% attrition. This is an area where HR should be aware of. HR should question the employee candidate why the employee quits the previous job and get in touch with previous company to have information about the applying employees. Besides that, the company should take precautionary measurements to keep their employees in their current role after they hire new employees.

- 32% of employees are single and has the highest attrition percentage(25.5%). The company should be aware of this important factor and have strategy to deal with this groups' performance.

- If the year increases since the employees' last promotion, the attrition percentage also displays increase. Especially, 7 years since last promotion employee group (5.2%) has the highest attrition(21.1%) in its individual group. For that reason, the company review their promotion policy, and maybe define the company's expectations from their employees and make clear to all employees how and when they may be promoted.

- 5.6% of employees works as Sales Representative and 17.6% of employees works as Laboratory Technician. They have 39.8% and 17.6% attrition percentage respectively. These two-job roles should be questioned, and the company should find the reason(s) why these job roles face more attrition rate than all others and take necessary actions.

- Beside those factors above, there are some other indicators which keep employees in the company. These factors are stated below.

- Total working years in the company,
- Years in current role,
- Environment satisfaction,
- Medical education field,
- job satisfaction,
- Job involvement,
- Years with current manager,
- Work life balance,
- Age.

The company should primarily try to increase the effectiveness of those factors. As a result, it will yield to the decrease in the attrition rate.

​

**If you wish to review the full in-depth EDA along with the predictive modeling portion, where i have developed a robust Machine Learning model based on the SVM classifier algorithm, and included the feature coefficients plot ,through which practical recommendations have been derived, kindly refer to my Jupyter notebook.**
