# DSA-CAPSTONE-PROJECT-1
An analysis project carried out on Palmoria Group HR data and submitted to Incubator hub for the Digital Skill up Africa (DSA) Data Analysis training.

### 👩‍💻Analyst: DebbieDiamond 
## Project Topic:🗜️Palmoria Group HR Analysis
### 📑Abstract:
This analysis examines the HR data of Palmoria Group, a Nigerian manufacturing company facing gender equality issues and recently labeled by the media as a 'Patriarchal Manufacturing Company.' Built with Power BI, the report presents a clean dashboard with calculated measures, visuals, and charts that provide recommendations for management's attention.
## 📝 Project Overview 
### Objective:
To analyze and visualize Palmoria Group's HR data to generate insights on **salaries**, **departments**, **regions**, and **ratings** of employees based on their **gender**, which the management team needs to address.

### ⚒️ Tools Used:
📑 Power Query Editor
- Data Extraction
- Data transformation and cleaning 🧹
   1. Filters
   2. Remove rows
- Data Loading 💬

🧰 Power BI
- Measures Calculation 📟
- Visuals Building  📊
## 🔮Data Cleaning and Preparation 
At the initial stage of data cleaning, the following actions were performed: 
- Data loading and inspection
- Handling "NULL" cells and blanks
- Assigning a generic name to employees who didn't disclose their gender.
## 🔦📈 Exploratory Data Analysis 
### 🔍 Key Business Questions Answered 
EDA was carried out to answer some key questions:
1. **Which region and departments should be the main focus based on gender pay gap?**
- **Region: South West**
- **Departments: Research and Development, Human Resources and Legal**
- The management needs to focus on these departments and the southwest region because they are the lowest paid.
2. **Does Palmoria group meets the requirements which requires manufacturing companiees to pay employees a minimum of $90,000?**
  - **No**, they don't.
3. **Calculate the total amount to be paid to individual employees (salary inclusive of 
bonus)**
- **$71.88M**
## 🔍📈 Data Analysis and Visual Insights 
The following analyses were carried out to create visuals and charts for insights. They are
1. **Gender distribution in the organization distiled to regions**
 ``` DAX
 Gender Count = 
COUNT(
Palmoria_Group_emp_data__2[Gender]
)
```
![image](https://github.com/user-attachments/assets/37fc3e6f-15be-4f53-ad1a-8611f0d01e34)

2. **Insights on ratings based on gender**
```DAX
Average Rating = 
AVERAGE(Palmoria_Group_emp_data__2[Bonus Rate])
```
![image](https://github.com/user-attachments/assets/7f85317d-46bf-439a-b614-6d1b6334f13b)

3.  **Payment distribution of employees grouped by band**
```Powerquery
= Table.AddColumn(
#"Removed Columns", "Salary Band",
each if [Salary] < 10000 then "0-10000"
else if [Salary] < 20000 then "10001-20000"
else if [Salary] < 30000 then "20001-30000"
else if [Salary] < 40000 then "30001-40000"
else if [Salary] < 50000 then "40001-50000"
else if [Salary] < 60000 then "50001-60000"
else if [Salary] < 70000 then "60001-70000"
else if [Salary] < 80000 then "70001-80000"
else if [Salary] < 90000 then "80001-90000"
else if [Salary] < 100000 then "90001-100000"
else if [Salary] < 110000 then "100001-110000"
else if [Salary] < 120000 then "110001-120000"
else null
)
```
## 📊 Analytics Dashboards
![Palmoria 1](https://github.com/user-attachments/assets/2653fbfd-5652-49e1-8a93-c4025435c786)
![Palmoria 2](https://github.com/user-attachments/assets/3917ec8e-463b-4024-a10e-ca4defabe1d0)
## 📝 Conclusion
This HR analysis of Palmoria Group shows a balanced gender distribution and slightly higher average ratings for females. While the total sum of female salaries is higher, there is a true gender pay gap (average individual earnings). The most critical finding is that 654 out of 946 employees currently earn below the new $90,000 minimum salary regulation, indicating Palmoria Group does not meet this requirement and needs urgent financial and strategic adjustments.

*✍️ Reported by Deborah Adegbemile*
*🗓️ Date: July, 2025*
