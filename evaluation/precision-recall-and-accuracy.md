# Precision, recall and Accuracy

## Single label case

### Precision, recall, specificity and accuracy

Precision, positive prediction value \(PPV\)

$$
\text{PPV} = \frac{tp}{tp+fp}
$$

Recall, sensitivity, hit rate, true positive rate \(TPR\)

$$
\text{TPR} = \frac{tp}{tp+fn}
$$

Specificity, selectivity, true negative rate \(TNR\)

$$
\text{TNR} = \frac{tn}{tn+fp}
$$

Accuracy

$$
\text{Accuracy} = \frac{tp+tn}{tp+tn+fp+fn}
$$

### Relationship between precision and recall

To fully evaluate the effectiveness of a model, you must examine **both** precision and recall. Unfortunately, precision and recall are often in tension. That is, improving precision typically reduces recall and vice versa.

![](../.gitbook/assets/precisionvsrecallbase.png)

### Sensitivity and specificity

$$
\text{Sensitivity} = \text{Recall}
$$

$$
\text{Specificity} = \frac{tn}{tn+fp}
$$

## Multi label case

$$
\text{Overall Accuracy} = \frac{\text{# of correctly classified samples}}{\text{# of samples}}
$$

## References

1. [Machine Learning Crash Course: Classification: Precision and Recall](https://developers.google.com/machine-learning/crash-course/classification/precision-and-recall)

