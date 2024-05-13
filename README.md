# Sales Team Performance Analysis Dashboard

![Screenshot 2024-05-13 140302](https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/80e09473-df6a-41e7-859f-29945da26512)

## Overview

This Power BI dashboard provides a comprehensive analysis of sales team performance. It offers insights into key metrics, revenue distribution, and performance trends. Whether you’re a sales manager or analyst, this dashboard helps you make informed decisions.

## Features

1. Total Transactions, Quantity, and Revenue:
Quickly view the overall performance metrics. Understand the scale of transactions, quantity sold, and total revenue.

2. Total Revenue by Manager:
Pie chart showing revenue distribution between managers. Helps to identify top-performing managers.

3. Total Revenue by Channel:
Pie chart displaying revenue split across different channels (Retail, Distributor, Online). Understand which channels contribute the most to overall revenue.

4. Monthly Revenue Trends:
Line-and-bar graph comparing actual revenue against budget using python script, special color coding for bar where revenue < budget
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

6. Top/Bottom 'n' ProductGroups / ProductName /Salesperson:
Table listing the top/bottom-performing peramenters based on revenue.



8. Supervisor Performance:
Table showing individual supervisor and manager performance.
Includes total revenue, quantity, and percentage contribution.

## Usage
Open the Power BI file (sales_unit_performance.pbix).
Interact with the visuals:
Explore revenue trends and channel performance.
Drill down into specific product groups.
Filter by year, product name, or salesperson.

![image](https://github.com/rohanshrma25/SalesTeam_PowerBI_Dashboard/assets/143126097/ae7f2231-c517-43be-8a3b-af8a93a3de61)


## Contributing
We welcome contributions! If you have suggestions, bug fixes, or feature requests, feel free to submit a pull request.
