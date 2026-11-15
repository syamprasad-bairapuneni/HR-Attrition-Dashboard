# HR Attrition Dashboard (Power BI)

An interactive one-page Power BI dashboard that explains why employees leave, using the IBM HR Analytics employee attrition dataset.

!\[HR Attrition Dashboard](screenshots/dashboard.png)

## Key findings

* **Overtime is the biggest driver.** Employees who work overtime leave at 30.53%, compared with 10.44% for those who don't, nearly three times the rate.
* **Attrition is highest in the first two years.** Employees with 0-2 years at the company leave at 29.82%, falling to 8.13% for those with 10+ years.
* **Sales has the highest department attrition** at 21%, followed by Human Resources (19%) and Research \& Development (14%).
* **Overall:** 237 of 1,470 employees left, an attrition rate of 16.12%.
* **Monthly income of leavers** is concentrated in Research \& Development (546K) and Sales (544K).

## Dataset

* **Source:** IBM HR Analytics Employee Attrition \& Performance, on Kaggle
* **File:** `WA\_Fn-UseC\_-HR-Employee-Attrition.csv`
* **Size:** 1,470 employees, 35 columns
* **Target column:** `Attrition` (Yes / No)

## Tools

* Power BI Desktop
* Power Query (data cleaning and columns)
* DAX (measures and calculated columns)

## Data model

* `Employees` is the fact table (one row per employee).
* `Department` and `JobRoles` are dimension tables. Each has a one-to-many relationship with `Employees`.

## Measures and columns

|Name|Type|Purpose|
|-|-|-|
|`Headcount`|Measure|Total employees|
|`Leavers`|Measure|Employees with Attrition = Yes|
|`Attrition Rate`|Measure|Leavers ÷ Headcount|
|`Overtime Attrition Rate`|Measure|Attrition rate for employees who work overtime|
|`Leaver Monthly Income`|Measure|Sum of monthly income for leavers|
|`AttritionFlag`|Column|1 if Attrition = Yes, else 0|
|`TenureBand`|Column|Years at company grouped into 0-2, 3-5, 6-10, 10+|
|`Overtime Status`|Column|"Works overtime" or "No overtime"|

## Dashboard page

* **Cards:** Overtime Attrition Rate, Headcount, Attrition Rate, Leavers
* **Attrition rate by department**
* **Overtime workers leave at nearly three times the rate**
* **Attrition rate by years at company**
* **Total monthly income of leavers by department**

## How to open

1. Download the IBM HR dataset from Kaggle and save the CSV in a folder.
2. Open `HR\_Attrition\_Dashboard.pbix` in Power BI Desktop.
3. If prompted, update the data source to point to your CSV file.

## Limitations

* The dataset is a sample created for learning. It isn't real company data, so the results show patterns, not causes.
* Overtime and attrition are linked in the data, but this dashboard does not prove overtime causes people to leave.

## Author

Syamprasad Bairapuneni
syamprasadbairapuneni@gmail.com

