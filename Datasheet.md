# Datasheet Template

## Motivation

- For what purpose was the dataset created? This dataset offers a comprehensive view of the factors influencing students' academic performance, making it ideal for educational research, development of predictive models, and statistical analysis.
- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset? It was created by Rabie El Kharoua. It is original and has never been shared before.

 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? It represents academic performances in the format of a document.
- How many instances of each type are there? There are 10 instances detailing their demographics, study habits, parental involvement, extracurricular activities, and academic performance. 
- Is there any missing data? No
- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)? The data is synthetic data, but if it were real data it might be considered confidential because it contains personal information about students inlcuding their age, ethnicity and student ID. 

## Collection process

- How was the data acquired? It is synthetic data created by the owner and aquired by me through Kaggle.
- If the data is a sample of a larger subset, what was the sampling strategy? It is not a sample of a larger subset.
- Over what time frame was the data collected? Unknown

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section.Yes, various preprocessing steps were applied: column removal, one-hot encoding, and numerical scaling.
- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? It is available on Kaggle, the processing of data was done on a copy. 
 
## Uses

- What other tasks could the dataset be used for? The dataset can be used for grade prediction, dropout risk analysis, student segmentation, personalized learning recommendations, and exploring factors influencing academic performance.
- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? Users might want to remove the 'Ethnicity' feature since it could lead to racial bias. 
- Are there tasks for which the dataset should not be used? If so, please provide a description. It should not be use to determine which students will be allowed into an institution and which not. For instance, it should not be used to predict a students capacity and thus reject or accept them from university.

## Distribution

- How has the dataset already been distributed? Via Kaggle.
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)? The Students Performance Dataset by rabieelkharoua on Kaggle does not specify a separate data license, which means it is governed by Kaggle's Terms of Use (ToU). 

## Maintenance

- Who maintains the dataset? Rabie El Kharoua. 
