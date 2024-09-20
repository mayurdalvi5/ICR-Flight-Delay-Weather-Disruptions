# Week 4
Week 4 updates including accomplishments, blockers, and next week's goals.

---

# This Week's Accomplishments

  - **Ella** researched **background** information on the significance of flight delays in the aviation industry and the impact of weather as a critical factor. She created a rough draft for the background and developed a **problem statement** and **objective** for the project. Ella's background summary, problem statement, and objective can be found in an attached file.
  - **Tristan** conducted a **literature review** of existing models and their weather data utilization. He reviewed three different papers that used different models such as decision trees, random forests, support vector machines, gradient boosting machines, and more. He analyzed the data usage of each paper as well as the resulting accuracy levels. Tristan's literature review can be found in an attached file.
  - **Mayur** focused on **data collection** and **web scraping** relevant to our problem statement. He identified reliable data sources for both weather and flight data, which came from different origins. To handle this, he developed scripts to fetch the respective data sets and successfully merged them into a single data set. 
  - **Reza** worked with Mayur on **data collection** and **initial data cleaning**. The initial data cleaning code can be found in the **Initial_data_exploration.ipynb**. Currently, they've been working with a smaller subset of data, specifically from New York and Colorado during January 2024. As they've been working on cleaning and compiling the data, they've run into a few questions which have been included in the following blocker section.

---

# Blockers and Questions
  
  - **Data collection and cleaning**
      - As we were looking through the data set located in **Initial_data_exploration.ipynb**, we noticed that there were a lot of NA values. How would you suggest we handle these?
      - In the data set, we also noticed that some flights had an earlier departure than scheduled (negative delay in minutes). We would love to get your insight on this, should we only consider observations that have been delayed for lengths of time greater than 0?
      - The aircraft type is not in the data set, how should we go about this?
      - In our classes we have learned that the more data, the better the model would be. But we would love to get your insight to this as well. How many data points should we collect? How many data points are enough in a project like this?

---

# Next Week's Goals

- **Ella** and **Tristan** will be working on combining the background, problem statement, objective, and literature review into a well-written **introduction**.
- **Mayur** and **Reza** will be moving forward with the data collection and cleaning based on the feedback we've received from the domain experts. Based on this feedback, they'll work on **improving data accuracy** and **expand the data set** to include the last 5 to 10 years and additional states if needed.

---
