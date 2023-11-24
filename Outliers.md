# Outliers

Outliers are values that are far from the mean. This means that if the values from an attribute follow a Gaussian/Normal distribution, the outliers are located at the tails.

Outliers can be global or local. The former group represents those values that are far from the entire set of values of a feature.

For example, when analyzing data from all members of a neighborhood, 
- a global outlier would be a person who is 180 years old (as shown in the following diagram (A)), represents values that are far from a subgroup of values of that feature.
- a local outlier would be a college student who is 70 years old (B), which would normally differ from other college students in that neighborhood

![image](https://github.com/sateeshfrnd/Feature-Engineering/assets/8160366/07726c71-c534-4370-bde3-f0f269867f87)

Considering both examples that have been given, outliers do not evaluate whether the value is possible. While a person aged 180 years is not plausible, a 70-year-old college student might be a possibility, yet both are categorized as outliers as they can both affect the performance of the model.

A straightforward approach to detect outliers consists of visualizing the data to determine whether it follows a Gaussian distribution, and if it does, classifying those values that fall between three to six standard deviations away from the mean as outliers. Nevertheless, there is not an exact rule to determine an outlier, and the decision to select the number of standard deviations is subjective and will vary from problem to problem.

For example, if the dataset is reduced by 40% by setting three standard deviations as the parameter to rule out values, it would be appropriate to change the number of standard deviations to four.

On the other hand, when dealing with text features, detecting outliers becomes even trickier as there are no standard deviations to use. In this case, counting the occurrences of each class value would help to determine whether a certain class is indispensable or not. For instance, in clothing sizes, having a size XXS that represents less than 5% of the entire dataset might not be necessary.

Once the outliers are detected, there are three common ways to handle them:
- **Delete the outlier:**
  - For outliers that are true values, it is best to completely delete them to avoid skewing the analysis. This may be a good idea for outliers that are mistakes, if the number of outliers is too large to perform further analysis to assign a new a value.
- **Define a top:**
  - Defining a top might also be useful for true values. For instance, if you realize that all values above a certain threshold behave the same way, you can consider topping that value with the threshold. 
- **Assign a new value:**
  - If the outlier is clearly a mistake, you can assign a new value using one of the techniques that we discussed for missing values (mean or regression imputation). 

The decision to use each of the preceding approaches depends on the outlier type and number. Most of the time, if the number of outliers represents a small proportion of the total size of the dataset, there is no point in treating the outlier in any way other than deleting it.
