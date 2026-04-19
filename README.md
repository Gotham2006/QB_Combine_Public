# CMSE202_Sports4
*Question: How do combine metrics correlate to NFL Production for different positions?*

                                  --Gautham Dineshkumar--
I parsed through a 120 records to find QB's that had significant enough playing time to consider their PFF scores and then manually inserted all these values and cleaned the data. The folder called QB Combine contains all the code that I did. I also did my part of the report and slides titled QB.

The dataset used is in the QB_Combine_Data.csv. 

For the Plot Generator, you can run QB_Plot_Generator.py and for the ML Models summaries you can run the QB_ML_Model.ipynb. The results for QB_ML_Model.ipynb shows up in the output terminal and the images for the Plot Generator are stored as pngs in the folder. 

I also stopped using a branch as my JupyterHub crashed multiple times when I tried to merge my branch with main.

                                    --Joseph Maleckas--

For the Wide Receiver dataset, I took the 2021 draft class and filtered them down to only the WR position. I then got the data for all of the Combine drills that are quantifiable for each of these WRs and added them to the dataset, while removing all NaNs or non-quantifiable data. Finally, for the dataset, I was able to search the internet for each of these Wrs average PFF grade since they entered the NFL, and manually implemented them into the dataset

In order to run this code you just need to run the entire Wr_Work_File.ipynb file using the sklearn linear regression function along with all other imports to assist in data cleaning and plotting of the data

                                    --Ishan Sinha--
For the Tight End analysis, our dataset was small, and we didn't have access to PFF grades. Instead, I used Pro Football Reference's Player Approximate Value (PlAV). To make this a classification problem, I calculated the median PlAV for the position and created a binary target (1 = "Hit" / Above Median, 0 = "Bust" / Below Median). I also had to use mean imputation to handle missing Combine data, as many prospects skip the 3-Cone drill.

You can find all my specific work in the TE_Analysis folder. The TE_Combine_Data.csv holds the cleaned data. Run TE_ML_Model.ipynb to see the machine learning pipeline, where I compared an optimized Support Vector Machine (SVM) against a Random Forest Classifier to predict NFL success. The Random Forest won out with a 78% accuracy. The exploratory data analysis and presentation visuals are also saved as images in this folder.

My laptop crashed once while I was working on the code and after I wasn't able to access the GitHub for some reason, so I have no branch. Instead, I manually downloaded all the files, edited them, and, before pushing, checked the github for any merge/file conflicts.


                                    --Connor Good--

For the Running Back analysis, when trying to find correlation between running back combine data and the performances and impact on the field, we used combine data and performance statistics taken from the years 2018-2023 as that was available for use. PFF data was not available to the public for running back data so the best way of determining how combine data effects impact on the field was to run a model through sklearn, and training the model based on combine data to find which combine events were the most impactful. In order to run the model just go through the running back folder and run all of the code from top to bottom, as the needed datasets should be included within the folder. This model determines running back production based on combine data using testing and training data over the given years that data was available. 


                                    