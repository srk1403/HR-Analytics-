**Problem Statement:**
The goal of this HR analytics report is to:

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

**2. Behavioral Metrics:**
- Job satisfaction (avg: 2.70), relationship satisfaction, and work-life balance were assessed.

**3. Career Progression:**
- Examined years in the current role (avg: 4.25), years since last promotion (avg: 2.21), and average salary hikes (15.20%).

**3] Behavioral Analysis:**
- Correlated job satisfaction, work-life balance, and relationship satisfaction with attrition.
- Highlighted low behavioral scores in Sales, HR, and Research roles as drivers of higher attrition.

**4] Career Progression Analysis:**
- Investigated whether career growth metrics like promotions and salary hikes influenced attrition.
- Found no direct correlation between career progression and attrition rates.

**5] DAX Formulae Used :**
**Behaviour Analysis -->**
Calculate the Attrition Rate :
**1. Attrition Rate** = DIVIDE(SUM(HR_Analytics[Attrition Qty]),COUNT(HR_Analytics[EmployeeCount]))
This is to calculate the Total Attrition Rate.

**2. AR JS** = CALCULATE([Attrition Rate], HR_Analytics[JobSatisfaction] <= 2.73)
Calculating the Attrition Rate of people having Job staisfaction less than Average less.
( The idea is to know how unsatisfied Employees are and leaving the company due to lower Job Satisfaction )

**2. AR RS** = CALCULATE([Attrition Rate],HR_Analytics[RelationshipSatisfaction]<= 2.76)
Calculating the Attrition Rate of people having Relationship staisfaction less than Average.

**3. AR WLB** = CALCULATE([Attrition Rate], HR_Analytics[WorkLifeBalance] <= 2.76)
Calculating the Attrition Rate of people having Work Life Balance less than Average.

Calculate the Average Metric of people Leaving :
**4. Avg_JS_AR** = CALCULATE(AVERAGE(HR_Analytics[JobSatisfaction]), HR_Analytics[Attrition] = "Yes")
- Finding out the Average Job Satisfaction of people leaving the company.

{ Similar process is followed for Relationship Satisfaction and Work Life Balance Metrics }

**Insights and Recommendations:**
Identified high attrition in specific departments (Sales, HR, Research) and roles (Lab Technicians, Sales Executives).
Suggested improvements in onboarding processes, cultural fit assessments, and employee engagement programs.
