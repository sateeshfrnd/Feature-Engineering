# Handling missing values
Most tables fed into machine learning problems are two-dimensional, meaning that they contain rows and columns. Conventionally, each row represents an observation (an instance), whereas each column represents a characteristic (feature) of each observation. *Features where a few instances have values, as well as instances where there are no values for any feature, are considered missing data.*

![image](https://github.com/sateeshfrnd/Feature-Engineering/assets/8160366/330aacfa-1656-4664-b5ee-644c0461d138)

Conventionally,*a feature missing more than 5 to 10% of its values is considered to be missing data*, and so needs to be dealt with. On the other hand, *all instances that have missing values for all features should be eliminated* as they do not provide any information to the model, and, on the contrary, may end up introducing bias.

When dealing with a feature with a high absence rate, it is recommended to either eliminate it or fill it with values. The most popular ways to replace the missing values are as follows:
- **Mean imputation:** Replacing missing values with the mean or median of the features' available values.
- **Regression imputation:** Replacing missing values with the predicted values obtained from a regression function.

While *mean imputation* is a simpler approach to implement, it may *introduce bias* as it evens out all instances in that matter. On the other hand, even though the *regression approach* matches the data to its predicted value, *it may end up overfitting the model* as all values introduced follow a function.

Lastly, when the missing values are found in a text feature such as gender, the best book of action would be to either eliminate them or replace them with a class labeled uncategorized or something similar. This is mainly because it is not possible to apply either mean or regression imputation over text.

Labeling missing values with a new category (uncategorized) is mostly done when eliminating them removes an important part of the dataset, and hence is not an appropriate book of action. In this case, even though the new label may have an effect on the model depending on the rationale used to label the missing values, leaving them empty is an even worse alternative as it causes the model to make assumptions on its own.
