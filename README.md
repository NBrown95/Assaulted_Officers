# Assaulted_Officers

This project will help predict and identify factors that may contribute to the assault of police officers. 

The source of this data is from the website https://data.louisvilleky.gov/dataset/assaulted-officers. This dataset contains information regarding officers who were assaulted on the Louisville Metropolitan Police Department (LMPD) in Kentucky from 2019 to Present.

I chose this topic because officers are currently working in one of the most hostile and stressful environments in the history of law enforcement. Using data and information to determine scenarios where officers are more likely to be assaulted may help reduce these incidents in the future. This can also lead to better training and/or a change in tactics regarding certain factors that increase likelihood of an assault on officers. Changing these tactics can increase officer safety. 

The main questions to be answered by this project are: What factors lead to assaults against officers? What are the most dangerous scenarios for officers? Can we predict assaults against officers?

Since this is a solo project, I will not need communication protocols or individual branches.

I imported the raw data files to jupyter notebook and used pandas to drop irrelevant columns and filter dataframes. I then exported these dataframes as csv files.

Next, I imported these csv files into tables I created in PostgreSQL. I then joined these tables on the incident number and exported this file as a csv file. Using Excel, I sorted and filtered the data and added a column that put a '1' if an officer was attacked during the encounter and a '0' if the officer was not attacked. I removed null values and reduced the number of columns for relevance. 

Finally, I imported this csv file into jupyter notebook to begin the machine learning model. I used pandas get_dummies package to encode the categories into binary labels. I used the newly created officer attacked column as the target variable and the rest of the dataframe as the features. I trained, scaled, and fit the data. I used RandomForestClassifier to predict features that may lead to officer attacks. 
