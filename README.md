**Problem Statement:**
- The goal of this HR analytics report is to:

**- Analyze Attrition:** Identify factors contributing to employee attrition (16.17%) across departments, age groups, education levels, and roles.

**- Understand Behavioral Factors:** Evaluate job satisfaction, work-life balance, and relationship satisfaction to assess their impact on attrition.

**- Examine Career Progression:** Assess metrics such as years in the current role, years since last promotion, and salary hikes to uncover their influence on attrition.

**- Provide Insights:** Derive actionable insights for improving employee retention and engagement.

**Steps Followed**
**1] Data Preparation:**
Consolidated data on employees’ demographics, compensation, behavioral scores, and career progression.
Segmented data by departments, roles, and salary brackets.

**2] Exploratory Data Analysis:**
**1.Attrition Analysis:**
- Total employees: 1,416.
- Attrition count: 229 (16.17%).
- Analyzed attrition across education levels, age groups, salary slabs, and roles.
<img width="731" alt="image" src="https://github.com/user-attachments/assets/0708f2a4-f6f5-4ae4-a81b-08ebfef2b1d6" />

**2. Behavioral Metrics:**
- Job satisfaction (avg: 2.70), relationship satisfaction, and work-life balance were assessed.

**3. Career Progression:**
- Examined years in the current role (avg: 4.25), years since last promotion (avg: 2.21), and average salary hikes (15.20%).

**3] Behavioral Analysis:**
- Correlated job satisfaction, work-life balance, and relationship satisfaction with attrition.
- Highlighted low behavioral scores in Sales, HR, and Research roles as drivers of higher attrition.
<img width="540" alt="image" src="https://github.com/user-attachments/assets/bb71d4d0-8cb6-492a-b5a3-d26bf27d80ef" />

**4] Career Progression Analysis:**
- Investigated whether career growth metrics like promotions and salary hikes influenced attrition.
- Found no direct correlation between career progression and attrition rates.
<img width="566" alt="image" src="https://github.com/user-attachments/assets/83fee569-fc32-4690-b0bd-558b91a8dee2" />

**5] DAX Formulae Used :**
**Behaviour Analysis -->**
Calculate the Attrition Rate :
**1. Attrition Rate** = DIVIDE(SUM(HR_Analytics[Attrition Qty]),COUNT(HR_Analytics[EmployeeCount]))
This is to calculate the Total Attrition Rate.

**2. AR JS** = CALCULATE([Attrition Rate], HR_Analytics[JobSatisfaction] <= 2.73)
Calculating the Attrition Rate of people having Job staisfaction less than Average.
( The idea is to know how unsatisfied Employees are and leaving the company due to lower Job Satisfaction )

**2. AR RS** = CALCULATE([Attrition Rate],HR_Analytics[RelationshipSatisfaction]<= 2.76)
Calculating the Attrition Rate of people having Relationship staisfaction less than Average.

**3. AR WLB** = CALCULATE([Attrition Rate], HR_Analytics[WorkLifeBalance] <= 2.76)
Calculating the Attrition Rate of people having Work Life Balance less than Average.

Calculate the Average Metric of people Leaving :
**4. Avg_JS_AR** = CALCULATE(AVERAGE(HR_Analytics[JobSatisfaction]), HR_Analytics[Attrition] = "Yes")
- Finding out the Average Job Satisfaction of people leaving the company.

{ Similar process is followed for Relationship Satisfaction and Work Life Balance Metrics }


**--> Career Progression Analysis:**
We would be doing the similar thing we did with Behavioural Analysis.

Calculate the Attrition Rate :
**5. AR YrsInCurrRole** = CALCULATE([Attrition Rate],HR_Analytics[YearsInCurrentRole] <= 15.2)
Calculating the Attrition Rate of people having Years in Current Role less than Average.

{ Similarly the Attrittion Rates are found out for : 
- Years in Last Promotion
- % salary hike

Calculate the Average Metric of people Leaving :
**6. Avg_%salaryhike_AR** = CALCULATE(AVERAGE(HR_Analytics[PercentSalaryHike]),HR_Analytics[Attrition]="Yes")

{ Similarly the Attrittion Rates are found out for : 
- Years in Last Promotion
- Years in Current Role

**Insights and Recommendations:**
- Identified high attrition in specific departments (Sales, HR, Research) and roles (Lab Technicians, Sales Executives).
- Suggested improvements in onboarding processes, cultural fit assessments, and employee engagement programs.
<img width="535" alt="image" src="https://github.com/user-attachments/assets/ce355c60-3644-4fbe-b3ed-1d0977824b08" />


