# ml-foundations-comparison

Comparing 6 classical ML algorithms on the Titanic survival dataset.

## Approach
- Cleaned missing values (Age median, Embarked mode, dripped Cabin)
- Encoded categorical features, scaled features for distance-based models
- Trained: Logistic Regression, Decision Tree, Random Forest, SVM, KNN
- Evaluatd on accuracy, precision, recall, F1

## Results
|      | Predicted 0 | Predicted 1 |
| --- | --- | --- |
| **Actual 0** | Correct => True Negative | Wrong => False Positive |
| **Actual 1** | Wrong => False Negative | Correct => True Positive |


![Confusion Matrix](confusion_matrix_KNN.png)

The 4 metrics to evaluate the trained models are...

- **Accuracy**: what fraction of all predictions were correct overall <br />
Correct: 97 + 51 = 148 <br />
Incorrect: 18 + 13 = 31 <br />
Total: 179 <br />
Overall Accuracy: 148/179 = 83%

- **Precision**: of the passengers the model predicted "survived", what fraction actually did ( measures false alarms) <br />
Correct suvivors: 51 <br />
Predicted survivors: 51 + 13 = 64 <br />
Precision: 51/64 = 78%

- **Recall**: of the passerngers who actually survived, what fraction did the model catch ( measures missed cases) <br />
Total survivors: 18 + 51 = 69 <br />
Caught survivors: 51 <br />
Recall: 51/69 = 74%


- **F1**: a single balanced score combining precision and recall (useful because recall can trade off against each other) <br />
F1 = 2 * (Precision * Recall) / (Precision + Recall) <br />
2 * (0.796875 * 0.73913) / (0.796875 + 0.73913) = 0.766917

## Takeaways
At first glance, I thought a simple avarage number of the Precision and the Recall, *the arithmetic means*, could suffice to evaluate the model due to its simplicity of calculation. However, application of the avarage hides the unbalanced score gap between the Precision and the Recall when one is significantly higher than the other. Thus, the F1, *the harmonic means*, is more trustworthy because the both value need to be high and balanced.