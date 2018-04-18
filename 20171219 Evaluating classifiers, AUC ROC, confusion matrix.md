# Terms
AUC: area under curve
ROC: receiver operating characteristics curve

baseline accuracy: percentage of majority class 

# KNN to predict 
spam detection: usually naive bayes

knn.fit(X, y)

knn.predict(X.iloc[0:10, :])

knn.predict_proba(X.iloc[0:10, :])
probability of all classes (ordered)

# Confusion matrix
focus on true negative and true positive
(must take up majority of the whole table)

ideally, falses must tend to 0

# manual calculation of confusion matrix
predicted = knn.predict(X)

tp = np.sum((y == 1) & (predicted == 1))
fp = np.sum((y == 0) & (predicted == 1))
tn = np.sum((y == 0) & (predicted == 0))
fn = np.sum((y == 1) & (predicted == 0))
print tp, fp, tn, fn

##### OR ######
from sklearn.metrics import confusion_matrix

confusion_matrix(y, predicted)

# type 2 error
statistical power
power = 1 - P(Type II error)

# Accuuracy
TP + TN / total popn

misleading in imbalanced cases

from sklearn.metrics import accuracy_score

print accuracy_score(y, predicted)

# recall / sensitivity
recall = tp / (tp + fn)

from sklearn.metrics import recall_score

print recall_score(y, predicted)

recall and precision are related inversely, balance tradeoff

# false positive
fpr = fp / (tn+fp)

# specificity / true negative
specificity = tn / (tn + fp)

# precision
precision = tp / (tp + fp)

from sklearn.metrics import precision_score

print precision_score(y, predicted)


# classification report
from sklearn.metrics import classification_report

print classification_report(y, predicted)

recall of smaller class will suffer when there is an imbalance

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.33)

# cost sensitive classificaiton
make false positive 0

# Receiver operating characteristic curve

see how accurate your model is

Looking at accuracy
the more cornered the ROC curve, the better the model

Refer to precision and recall to check accuracy. NOT REFLECTED in ROC curve


from sklearn.metrics import roc_curve, auc
# For class 1, find the area under the curve
fpr, tpr, _ = roc_curve(y_test, Y_pp.class_1_pp)
roc_auc = auc(fpr, tpr)


# Plot of a ROC curve for class 1 (has_cancer)
plt.figure(figsize=[8,8])
plt.plot(fpr, tpr, label='ROC curve (area = %0.2f)' % roc_auc, linewidth=4)
plt.plot([0, 1], [0, 1], 'k--', linewidth=4)
plt.xlim([-0.05, 1.0])
plt.ylim([-0.05, 1.05])
plt.xlabel('False Positive Rate', fontsize=18)
plt.ylabel('True Positive Rate', fontsize=18)
plt.title('Receiver operating characteristic for cancer detection', fontsize=18)
plt.legend(loc="lower right")
plt.show()

# do classification report then do ROC curve

check support levels, 50/50 ROC curve is believable