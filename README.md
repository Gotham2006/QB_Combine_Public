# CMSE202_Sports4
Question How do combine metrics correlate to NFL Production for different positions?

Gautham Dineshkumar
I parsed through a 120 records to find QB's that had significant enough playing time to consider their PFF scores and then manually inserted all these values and cleaned the data. The folder called QB Combine contains all the code that I did. I also did my part of the report and slides titled QB.

Dataset
The dataset used is in the QB_Combine_Data.csv.

For the Plot Generator, you can run QB_Plot_Generator.py and for the ML Models summaries you can run the QB_ML_Model.ipynb. The results for QB_ML_Model.ipynb shows up in the output terminal and the images for the Plot Generator are stored as pngs in the folder. 

I also stopped using a branch as my JupyterHub crashed multiple times when I tried to merge my branch with main.

Joseph Maleckas

For the Wide Receiver dataset, I took the 2021 draft class and filtered them down to only the WR position. I then got the data for all of the Combine drills that are quantifiable for each of these WRs and added them to the dataset, while removing all NaNs or non-quantifiable data. Finally, for the dataset, I was able to search the internet for each of these Wrs average PFF grade since they entered the NFL, and manually implemented them into the dataset

In order to run this code you just need to run the entire Wr_Work_File.ipynb file using the sklearn linear regression function along with all other imports to assist in data cleaning and plotting of the data
