# Data Simulation

Using the [Boston dataset](https://www.cs.toronto.edu/~delve/data/boston/bostonDetail.html#:~:text=The%20Boston%20Housing%20Dataset,the%20area%20of%20Boston%20Mass.&text=It%20was%20obtained%20from%20the,the%20literature%20to%20benchmark%20algorithms.), a new dataset is simulated with over 29,000 records. These include created variables (median_income that is highly correlated with the median housing prices and population and families that are highly correlated with one another).  

The new records were simulated with [SMOTE](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.over_sampling.SMOTE.html) and several transformations to manipulate outcomes were performed using numpy.random functions.  

Finally, the variable "sales" is added to the dataset, which can be average sales from a company in a county for a given set of months. This variable is a linear combination of the other variables (all weights assigned through trial and error until the author liked the outcome) with a random error applied to it. Sales that are lower than a certain amount are lifted up so that a small peak exists on the variable's left tail, making its distribution somewhat bimodal. This is done so that more advanced regression techniques, such as neural network, can predict the outcome better than linear regression, which likes normal distributions.  

The two resulting datasets, new.csv and existing.csv, are random draws from the created dataset of about 7,000 and 21,000 obserations respectively. A random county_id variable is added to both. The sales variable is dropped from existing, meaning it can be a new dataset used to make predictions on unknown data.  

This project is in service of another I am working on completing.