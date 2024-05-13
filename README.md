# Sales Team Performance Analysis Dashboard

![Screenshot 2024-05-13 140302](https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/80e09473-df6a-41e7-859f-29945da26512)

## Overview

This Dynamic Power BI dashboard provides a comprehensive analysis of sales team performance. It offers insights into key metrics, revenue distribution, and performance trends. Whether you’re a sales manager or analyst, this dashboard helps you make informed decisions.

## Features

**1. Filter Dashboard by Year:**  
New table made specifically for date bifurcation

<figure>
  <img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/86998541-023d-420f-940e-22fcd40e0375" alt="Power BI Dashboard" style="width:500px">
</figure>  
  
**2. Monthly Revenue Trends:**  
Line-and-bar graph comparing actual revenue against budget using python script, special color coding for column where revenue is less than budget
```
dataset = pandas.DataFrame(Total Budget, Total Revenue, Month, Year)
dataset = dataset.drop_duplicates()

import matplotlib.pyplot as plt
import pandas as pd

bar_colors = ['r' if revenue < budget else '#1d4259' for revenue, budget in zip(dataset['Total Revenue'], dataset['Total Budget'])]

fig, ax = plt.subplots(figsize=(9, 3))

plt.bar(dataset['Month'], dataset['Total Revenue'], color=bar_colors, label='Total Revenue')

ax2 = ax.twinx()
ax2.plot(dataset['Month'], dataset['Total Budget'], color='#5fadde', marker='o', label='Total Budget')

ax.set_ylabel('Total Revenue')
ax2.set_ylabel('Total Budget')

ax.set_ylim(0, max(max(dataset['Total Revenue']), max(dataset['Total Budget'])))
ax2.set_ylim(0, max(max(dataset['Total Revenue']), max(dataset['Total Budget'])))

ax.legend(loc='upper left',fontsize='large',bbox_to_anchor=(0.03, 1.1))
ax2.legend(loc='upper right',fontsize='large',bbox_to_anchor=(0.29, 0.95))

plt.style.use('classic')

ax.spines['top'].set_visible(False)
ax2.spines['top'].set_visible(False)

plt.show()
```

**3. Top/Bottom 'n' ProductGroups / ProductName /Salesperson:**  
Bar chart shows top pr bottom product name, product group or salesman (according to revenue) upon selection in muptiple parameters.  

Step1: Created a numeric range parameter to let the user select the number of parameters to show  
<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/a06d6f0c-a21a-430c-9db0-b7587704e101" width="600" height="500">

Step2: Created a table to select the order (top/bottom)    
<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/88152139-f056-438c-95ad-574a97c169ea" width="150" height="100">

Step3: Created a fields parameter to let user select the parameter the display in bar chart   
<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/1560ed4e-dd4f-476e-8c9b-ef3b9531d3bc" width="700" height="550">

Step4: Created a measure which connects both the parameters and the table discussed above  
<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/31233022-2deb-4917-b4b6-6e1eda0fda64" width="700" height="400">

Step5: Created a dynamic title that changes with selection   
<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/89305fce-1d48-40c8-85bb-f32192b41891" width="650" height="200">

**4. Supervisor Performance:**  
Table showing individual supervisor and manager performance.
Includes measures for total revenue, quantity, and percentage of total.

<figure>
  <img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/7a62e8d8-46a0-4532-a039-2673835be951" alt="Power BI Dashboard" style="width:500px">
  <figcaption>Measure to calculate percentage of total</figcaption>
</figure>

**5. Total Transactions, Quantity, and Revenue:**  
Quickly view the KPI's. Understand the scale of transactions, quantity sold, and total revenue.

**6. Total Revenue by Manager:**  
Pie chart showing revenue distribution between managers. Helps to identify top-performing managers.

**7. Total Revenue by Channel:**  
Pie chart displaying revenue split across different channels (Retail, Distributor, Online). Understand which channels contribute the most to overall revenue. Customised tooptip shows top salespeople for each channel

<img src="https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/c6bfc330-99b8-4aab-961c-e2527d00335b" width="500" height="400">

## Usage
Open the Power BI file (SalesTeamDashboard.pbix).  
Interact with the visuals:  
Explore revenue trends and channel performance.
Drill down into specific product groups.
Filter by year, product name, or salesperson.


## Contributing
Contributions are welcomed! If you have suggestions, bug fixes, or feature requests, feel free to submit a pull request.
