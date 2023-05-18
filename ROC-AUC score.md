### Short description
**link:** [link](https://towardsdatascience.com/intuition-behind-roc-auc-score-1456439d1f30)
**note:** intuition behind ROC-AUC score
**type:** 
**tag:**

### Summary
ROC-AUC is indicative of degree of **separability**/distinction or **intermingling**/crossover between the predictions of the two classes. Higher the score, higher the distinction and lower the crossover of the predictions of the two classes.

**ROC-AUC = 1**
![[Pasted image 20220802154319.png]]


In below example we can't clearly set probability level to separate Class 0 and Class 1 entirely. Because of that AUC-ROC have to be < 1, even if we maximalize AUC-ROC value.
![[Pasted image 20220802154547.png]]

Higher the crossover/intermingling is, lower is the ROC-AUC score. Hence, a higher ROC-AUC is always regarded better than a lower one.

0 <= ROC-AUC <= 1
Random classifier would have ROC-AUC ~ 0.5

**Comparison with log-loss**
Higher ROC-AUC always means lower log-loss. 
ROC-AUC does not account for how far predictions fall to actual values. Log-loss is lower farther the 0/1 demarcation line is from actual values.

![[Pasted image 20220802155709.png]]

TTR (true positive rate) - 
![[Pasted image 20220803120718.png]]

### Further reading 


