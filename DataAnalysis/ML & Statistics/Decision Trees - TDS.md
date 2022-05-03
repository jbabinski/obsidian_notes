### Short description
**link:** [link](https://towardsdatascience.com/decision-tree-classifier-explained-in-real-life-picking-a-vacation-destination-6226b2b60575)
**note:** decision tree classifier - notes on what's that and how to use it
**type:** #application
**tag**: #in_progress

### Summary
**Decision trees** can perform both classification and regression tasks, so you’ll see authors refer to them as **CART algorithm: Classification and Regression Tree**. This is an umbrella term, applicable to all tree-based algorithms, not just decision trees.

When you ask a question you're adding a **node**. 
- the first node is the **root** **node**. 
- the last node after the split the last node is called a **leaf node**.

Every time you answer a question you:
- create a **branch**
- segment the feature space into **region**

![[Pasted image 20220501205807.png]]

The goal is to continue to _splitting_ the feature space, and applying rules, until you don’t have any more rules to apply or no data points left.


- pure leaf node - leaves belong to a single class 
- mixed leaf node - leaves may have 2 classes
![[Pasted image 20220501211534.png]]



