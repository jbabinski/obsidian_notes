### Short description
**link:** [link](https://en.wikipedia.org/wiki/Variance_inflation_factor)
**note:** 
**type:** 
**tag:**

Code - check VIF values for X vector

	from patsy import dmatrices
	import statsmodels.api as sm
	from statsmodels.stats.outliers_influence import variance_inflation_factor
	
	vif = pd.DataFrame()
	vif["VIF Factor"] = [variance_inflation_factor(X.values, i) for i in range(X.shape[1])]
	vif["features"] = X.columns
	vif.round(1)
