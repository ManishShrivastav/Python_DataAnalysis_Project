# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles?

To find the most demanded skills for the top 3 most popular data roles, I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing what skills I should pay attention to depending on the role I am interested to get into.

View my notebook with detailed steps here: [2_skill_Demand.ipynb](3_Project\2_Skills_Demand.ipynb)

### Visualize Data

```python
fig, ax = plt.subplots(len(job_titles), 1)


for i, job_title in enumerate(job_titles):
    df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
    sns.barplot(data=df_plot, x = 'skill_percent', y='job_skills', ax=ax[i], palette='dark:b')

plt.show()
```

### Results

![Visualization of Top Skills for Data Experts](3_Project\images\skill_demand_all_data_roles.png)

### Insights

- Python is a versatile skill highly sought after across all three roles in data (Data Analyst, Data Engineer, Data Scientist), with particularly high demand among Data Scientists (72%) and Data Engineers (65%).
- Data Engineers necessitate specialized technical skills such as AWS, Azure, and Spark, whereas Data Analysts and Data Scientists are expected to excel in more broadly applicable data management and analysis tools like Excel and Tableau.
- SQL emerges as the top skill requirement for Data Analysts and Data Scientists, appearing in over half of the job postings for both roles. Conversely, Python is the predominant skill sought after for Data Engineers, featured in 68% of job postings.

## 2. How are in-demand skills trending for Data Analysts?

### Visualize Data

```python

from matplotlib.ticker import PercentFormatter

df_plot = df_DA_US_percent.iloc[:, :5]
sns.lineplot(data=df_plot, dashes=False, legend='full', palette='tab10')

plt.gca().yaxis.set_major_formatter(PercentFormatter(decimals=0))

plt.show()

```

### Results

![Trending Top Skills for Data Analysts in the US](3_Project\images\DA_skills_trend.png)
*Bar graph visualizing the trending top skills for data analysts in the US in 2023.*

### Insights
- SQL remains the dominant skill, highlighting its foundational role in data analysis despite a gradual decline.
- Excel maintains a significant presence, reflecting its versatility and widespread use, with a notable recovery in demand towards the year-end.
- Python is consistently important, emphasizing its relevance for programming, data manipulation, and analysis.
- Tableau shows a stable demand, indicating the ongoing need for robust data visualization tools.
- Power BI is less prominent but still necessary, suggesting it is a valuable but not primary skill for data analysts.