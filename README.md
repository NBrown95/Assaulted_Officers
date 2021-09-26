# Assaulted Officers

This project will help predict and identify factors that may contribute to the assault of police officers. 

The source of this data is from the website https://data.louisvilleky.gov/dataset/assaulted-officers. This dataset contains information regarding officers who were assaulted on the Louisville Metropolitan Police Department (LMPD) in Kentucky from 2019 to Present.

I chose this topic because officers are currently working in one of the most hostile and stressful environments in the history of law enforcement. Using data and information to determine scenarios where officers are more likely to be assaulted may help reduce these incidents in the future. This can also lead to better training and/or a change in tactics regarding certain factors that increase likelihood of an assault on officers. Changing these tactics can increase officer safety. 

The main questions to be answered by this project are: What factors lead to assaults against officers? What are the most dangerous scenarios for officers? Can we predict assaults against officers?

I imported the raw data files to jupyter notebook and used pandas to drop irrelevant columns and filter dataframes. I then exported these dataframes as csv files.

Next, I imported these csv files into tables I created in PostgreSQL. I then joined these tables on the incident number and exported this file as a csv file. Using Excel, I sorted and filtered the data and added a column that put a '1' if an officer was attacked during the encounter and a '0' if the officer was not attacked. I removed null values and reduced the number of columns for relevance. 

Finally, I imported this csv file into jupyter notebook to begin the machine learning model. I used pandas get_dummies package to encode the categories into binary labels. I used the newly created officer attacked column as the target variable and the rest of the dataframe as the features. I trained and resampled the data with SMOTE. This oversampled the assaulted officers data in order to predict assaults accurately. The balanced accuracy score of the SMOTE model was over 90% with a 0.95 f1 score. However, the precision score of the assaulted officer predictions was only 0.27. Therefore, the model is not great at predicting when officers will be attacked but is excellent at predicting when officers will not be assaulted. 

## Key Findings

* 11% of assaults on highways, roads, and alleys end with an assaulted officer
* 32% of assaults that are classified as “Menacing” result in an assaulted officer
* Jails, roads, and drug stores are locations with highest coefficients relating to assaulted officers

Link to presentation slides: https://docs.google.com/presentation/d/1--v6UNDhjtPhDgON7yDDuh8yEOWAh3PCToknc0l_FGI/edit#slide=id.p

Link to Tableau dashboard: https://public.tableau.com/app/profile/nathan5690/viz/LMPDOfficerAssaults/Story1?publish=yes
