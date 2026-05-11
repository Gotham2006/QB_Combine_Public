# Predicting NFL QB Success: Machine Learning Insights from Combine Data (2016–2021)

![Combine Picture](QB%20Combine/Plots/NFL_Scouting_Combine_logo.svg)

I initally started this project for my CMSE 202 class at Michigan State University. I wanted to combine my interest in sports with my interest in machine learning models and I chose combine data as my dataset as the 2026 combine was happenign when I presented my project proposal. In that original project, my group built singular models to predict player success; I specifically handled the machine learning models for the Quarterback position as Lamar Jackson is my favorite player.

I wanted to take those early concepts and upgrade them into a proper, object-oriented enterprise machine learning pipeline. I wanted to finish what I started. This program ingests historical NFL Combine data (2016–2021), trains an ensemble of models on raw athletic traits, to see what combine factors had the greatest correlation.

![Plot](QB%20Combine/Plots/qb_Broad_Jump_inches.png)

## The Methods

### ELT Pipeline

I first created an ELT pipeline for my machine learning models. I scoured the internet for free combine data and then used a python script to remove datasets which did not contain players that had played atleast 4 years in the NFL. I then further transforemed the data by finding the PFF score of the QB's who filled the required threshold and then removed players who did not have statistically significant PFF scores.

### OLS Regression 

I began by implementing OLS (Ordinary Least Squares) to analyze the linear relationship between athletic traits and raw PFF scores. This was what I did for my initial project. 

### Logistic Regression 

I then created a Logistic Regression Model to see if there were features that could help predict the difference between above and below median QB's. I then used StandardScaler, followed by Lasso to identify optimized features. I implemented Logistic Regression to transform the analysis into a classification task. By splitting the QBs into "Above Median" and "Below Median" performance tiers, the model calculated the specific probability of a prospect’s transition to the NFL being successful based on their refined athletic profile and helped identify if there was any collinearity.

### Random Forest Classifier

To account for non-linear relationships, I implemented a Random Forest model. This approach allowed me to rank Feature Importance and provide stability, revealing which specific physical tools carried the most weight in predicting professional success. 

### Gradient Boosting

I utilized Gradient Boosting to improve prediction accuracy through sequential error correction. This model was particularly valuable for handling the high variance inherent in sports data; by focusing on "difficult-to-classify" prospects in previous iterations, it provided a more refined look at players who might lack "prototypical" size but possess elite speed or agility.

## Limitations and Constraints

1. Sample Size (N=37): With an extremely small sample size of only 37 players, my models predictions cannot claim to have great statistical significance. It also makes outliers more statistcally significant then they shoudl be unless they are true freaks of nature like Lamar Jackson or Jayden Daniels (40-Yard dashes).

2. PFF grades: Well PFF grades are a good choice for my models as they provide me a singular value, it is not all encompassing and is not a perfect representation of their value.
   
## Takeaways

1. The "Speed" Signal is King
   Across all models, the 40-yard dash emerged as the most critical predictor. In the Gradient Boosting model, it accounted for over 35% of the feature importance. The negative coefficient in the Lasso Logit model            indicates that lower 40-yard dash times (faster players) are significantly associated with a higher probability of being an above-median PFF performer.
   
2. Explosiveness vs. Static Size
   Interestingly, Broad Jump was consistently the second or third most important metric.In the OLS model, Broad Jump had the highest positive coefficient (7.53), suggesting that lower-body explosiveness is a more reliable    predictor than simple height or weight.Static size (Height/Weight) showed low importance or even negative correlations, hinting that the "traditional pocket passer" archetype is being outperformed by more athletic,        mobile prospects in the modern era.
  
3. Model Performance & Stability
   Gradient Boosting was the superior model, achieving a 70.7% cross-validation accuracy. It also proved to be the most stable, with the lowest standard deviation (0.15) compared to the Logit model (0.28). Lasso              Regularization successfully reduced noise by isolating Broad Jump, Weight, and the 40-yard dash as the primary drivers of success, effectively "zeroing out" less impactful metrics like the Shuttle run or 3-Cone drill      for the classification task.
   
## Conclusion

The analysis reveals a clear shift in what physical traits correlate with modern NFL quarterback success. While traditional scouting often emphasizes "stature," the data suggests that explosiveness and mobility are much stronger signals for early-career performance.

The largest correlations occurred for the Broad Jump and 40-yard dash. This aligns with the modern NFL’s shift toward mobile quarterbacks, where the 40-yard dash measures speed and scramble potential; Broad Jump serves as a proxy for lower-body explosiveness, the source of arm strength.

![THE GOAT](QB%20Combine/Plots/Lamar_Jackson.jpg)

## How to Use & Repurpose This Repository

1. Fork the repository
2. cd "QB Combine"
3. Run Data_Cleaning/QB_Combine_Data_generator.ipynb
4. Run QB_Plot_Generator.ipynb
5. Run QB_ML_Model
6. All the results are in their respective folder.
