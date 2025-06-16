# Model Card

## Model Description

**Input:** Describe the inputs of your model 

Inputs after feature selection
Gender: Gender of the students, where 0 represents Male and 1 represents Female. Transformed to categorical feature to take into account 0.
ParentalEducation: The education level of the parents, coded as follows:
0: None
1: High School
2: Some College
3: Bachelor's
4: Higher
Transformed to categorical feature to take into account 0.

StudyTimeWeekly: Weekly study time in hours, ranging from 0 to 20.
Absences: Number of absences during the school year, ranging from 0 to 30. Transformed to categorical feature to take into account 0.
Tutoring: Tutoring status, where 0 indicates No and 1 indicates Yes. Transformed to categorical feature to take into account 0.

ParentalSupport: The level of parental support, coded as follows:
0: None
1: Low
2: Moderate
3: High
4: Very High
Transformed to categorical feature to take into account 0.

Extracurricular: Participation in extracurricular activities, where 0 indicates No and 1 indicates Yes. Transformed to categorical feature to take into account 0.
Sports: Participation in sports, where 0 indicates No and 1 indicates Yes. Transformed to categorical feature to take into account 0.
Music: Participation in music activities, where 0 indicates No and 1 indicates Yes. Transformed to categorical feature to take into account 0.
Volunteering: Participation in volunteering, where 0 indicates No and 1 indicates Yes. Transformed to categorical feature to take into account 0.

**Output:** Describe the output(s) of your model

GradeClass: Classification of students' grades based on GPA:
0: 'A' (GPA >= 3.5)
1: 'B' (3.0 <= GPA < 3.5)
2: 'C' (2.5 <= GPA < 3.0)
3: 'D' (2.0 <= GPA < 2.5)
4: 'F' (GPA < 2.0)

**Model Architecture:** Describe the model architecture you’ve used

1. Model Type
Decision Tree Classifier

Used for a classification task: predicting students' academic performance (GradeClass) as numerical outcomes (0, 1, 2, 3, 4).

2. Structure
The model is structured as a multi-class tree.

Each internal node represents a decision rule based on a feature (e.g., “Study Hours ≤ 2.5”).

Each branch represents the outcome of the decision (true/false).

Each leaf node assigns a final class label (0, 1, 2, 3 or 4).


3. Splitting Criteria
The decision tree uses a splitting criterion to choose the best feature at each node:

While choosing model: Gini impurity (default in most libraries like scikit-learn)

Used after tuning: Entropy (information gain)

4. Hyperparameters
Maximum depth: 15

Splitting criterion: entropy (information gain)

Max features considered per split: square root of total features (sqrt)

Minimum samples per leaf: 2

Minimum samples required to split a node: 5

Random state set to 2 for reproducibility


5. Interpretability
Highly interpretable: you can visualise the entire tree structure.

Also includes a feature importance graph to visualise which features had the highest impact.


## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

Testing set score 0.6709429121231558
Train set score 0.940567853705486
Val set score 0.8652982681205901

Final result for the Test Data Set

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.88      | 0.57   | 0.69     | 630     |
| 1     | 0.65      | 0.80   | 0.71     | 693     |
| 2     | 0.64      | 0.70   | 0.67     | 703     |
| 3     | 0.63      | 0.56   | 0.59     | 586     |
| 4     | 0.63      | 0.70   | 0.66     | 506     |

**Accuracy:** 0.67  
**Macro avg:** Precision 0.69, Recall 0.67, F1-score 0.67  
**Weighted avg:** Precision 0.69, Recall 0.67, F1-score 0.67  

Accuracy:
The proportion of total correct predictions out of all predictions made.
Formula: (Correct Predictions) / (Total Predictions)
What it tells me: How often the model is right overall.

Precision (per class):
Of all instances predicted as a particular class, how many were actually that class?
Formula: True Positives / (True Positives + False Positives)
What it tells me: How reliable the model’s positive predictions are for each class.

Recall (Sensitivity or True Positive Rate, per class):
Of all actual instances of a class, how many did the model correctly identify?
Formula: True Positives / (True Positives + False Negatives)
What it tells me: How well the model finds all instances of each class.

F1-Score (per class):
The harmonic mean of precision and recall, balancing the two metrics.
Formula: 2 × (Precision × Recall) / (Precision + Recall)
What it tells me: A combined measure of accuracy in terms of positive prediction correctness and completeness.

Support (per class):
The number of actual occurrences of the class in the test data.
What it tells me: How many samples of each class the metrics are calculated from.

Macro Average:
The simple average of the metric (precision, recall, or F1) calculated independently for each class.
What it tells me: Performance equally weighted across all classes, regardless of class size.

Weighted Average:
The average of the metric weighted by the number of instances (support) for each class.
What it tells me: Performance that takes into account the class distribution, emphasizing larger classes.

The model is reasonably balanced across classes. 
Class-specific metrics indicate some classes are harder to predict accurately, suggesting possible class imbalance or feature overlap.

## Limitations

Outline the limitations of your model.

Overfitting:
The large gap between training accuracy (~94%) and test accuracy (~67%) suggests the model overfits the training data and struggles to generalize to unseen data.

Limited Generalization:
The performance drop on the test set indicates the model may not fully capture the underlying patterns or is sensitive to noise or variations in the data.

Class Imbalance:
Some classes have lower recall or precision, possibly due to imbalanced class distribution, making it harder for the model to predict minority classes accurately.

Feature Interaction Constraints:
Decision trees split on single features at a time, which might miss complex interactions between multiple features impacting student performance.


## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 

Bias vs. Variance:

A deeper tree (max depth = 15) reduces bias by fitting training data closely but increases variance, causing overfitting and poor generalisation to new data (as seen in the test set accuracy drop).

Shallower trees reduce overfitting but may underfit, missing important patterns.

Interpretability vs. Complexity:

Deeper trees are less interpretable because of many splits, making it harder to extract simple, actionable rules.

Simpler trees are easier to understand but might not capture nuanced relationships.

Handling of Class Imbalance:

The model may perform well on majority classes but struggle with minority classes, leading to uneven precision and recall across classes. 

Accuracy: 

Another model such as random forest might have been better at classification but that would have meant a sacrifice in the interpretation which was a trade-off I was not willing to do in this case. Interpretability was more important. 
