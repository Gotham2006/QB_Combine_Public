# Predicting NFL QB Success: Machine Learning Insights from Combine Data (2016–2021)

![Motivation](QB%20Combine/Plots/NFL_Scouting_Combine_logo.svg)

I initally started this project for my CMSE 202 class at Michigan State University. I wanted to combine my interest in sports with my interest in machine learning models and I chose combine data as my dataset as the 2026 combine was happenign when I presented my project proposal. In that original project, my group built singular models to predict player success; I specifically handled the machine learning models for the Quarterback position as Lamar Jackson is my favorite player.

I wanted to take those early concepts and upgrade them into a proper, object-oriented enterprise machine learning pipeline. I wanted to finish what I started. This program ingests historical NFL Combine data (2016–2021), trains an ensemble of models on raw athletic traits, to see what combine factors had the greatest correlation.

## The Methods

### ETL Pipeline

I first created an ELT pipeline for my machine learning models. I scoured the internet for free combine data and then used a python script to remove datasets which did not contain players that had played atleast 4 years in the NFL. I then further transforemed the data by finding the PFF score of the QB's who filled the required threshold and then removed players who did not have statistically significant PFF scores.

### OLS Regression 

I began by implementing OLS (Ordinary Least Squares) to analyze the linear relationship between athletic traits and raw PFF scores. To refine my feature set and prevent overfitting on a smaller sample size, I applied Lasso Regression. By using L1 Regularization, the model automatically performed feature selection by shrinking the coefficients of less impactful variables to zero. 

### Logistic Regression 

Using the optimized features identified by Lasso, I implemented Logistic Regression to transform the analysis into a classification task. By splitting the QBs into "Above Median" and "Below Median" performance tiers, the model calculated the specific probability of a prospect’s transition to the NFL being successful based on their refined athletic profile.





## Conclusions & Takeaways

![Overall 2026 Draft Class Average Hybrid Score](assets/Overall_Draft_Grades.png)

Based on the final evaluation, the Minnesota Vikings walked away with the best overall draft class among the teams I tracked, scoring an average Hybrid Score of 1.960 per drafted player. This was heavily anchored by their high-upside defensive line picks.

Building an A/B ensemble taught me how to effectively balance algorithmic strengths. I used a Support Vector Machine as a stable, linear baseline, pairing it with a Random Forest Regressor to capture complex, non-linear trait intersections like size-adjusted speed. Blending these models into a single Hybrid Score ultimately mitigated their individual blind spots and produced a much more reliable evaluation than any single algorithm could achieve.

This project was a major learning experience for me in a few ways:
1. **Modular Python:** I learned how to properly separate concerns. Moving data cleaning, model training, and orchestration into their own isolated scripts (data_cleaner.py, predictor.py, team_grader.py) makes the code infinitely easier to debug and scale.
2. **Handling Missing Data:** I built strict drop logic. If a player was not invited to the Combine or did not run the required drills, the pipeline refuses to hallucinate dummy stats to score them. This maintains mathematical integrity and explains why a few late-round picks are missing from the final outputs.
3. **Advanced ML Techniques:** Upgrading from basic linear regressions to an ensemble method utilizing Random Forests and OHE drastically improved the model's ability to evaluate complex, real-world data.

## How to Use & Repurpose This Repo
