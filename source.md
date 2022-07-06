#Task 1: Import the data, drop duplicate rows, and inspect the data.
```
import pandas as pd
apps_with_duplicates = pd.read_csv('datasets/googleplaystore.csv')
apps = apps_with_duplicates.drop_duplicates()
print('Total number of apps in the dataset = ', apps.count())
print(apps.sample(5))
```
#Task 2: Clean the dataset.

```# List of characters to remove
chars_to_remove = ['+',",","$"]
# List of column names to clean
cols_to_clean = ['Installs','Price']

# Loop for each column in cols_to_clean
for col in cols_to_clean:
    # Loop for each char in chars_to_remove
    for char in chars_to_remove:
        # Replace the character with an empty string
        apps[col] = apps[col].apply(lambda x: x.replace(char, ''))
        
# Print a summary of the apps dataframe
print(apps.info())
```
#Task 3:Convert Installs and Price columns to float data type
import numpy as np

```# Convert Installs to float data type
apps['Installs'] = apps['Installs'].astype(float)

# Convert Price to float data type
apps['Price'] = apps['Price'].astype(float)

# Checking dtypes of the apps dataframe
print(apps.info())
```


#Task 4: With more than 1 billion active users in 190 countries around the world, Google Play continues to be an important distribution platform to build a global audience. For businesses to get their apps in front of users, it's important to make them more quickly and easily discoverable on Google Play. To improve the overall search experience, Google has introduced the concept of grouping apps into categories.

This brings us to the following questions:

Which category has the highest share of (active) apps in the market?

Is any specific category dominating the market?

Which categories have the fewest number of apps?

We will see that there are 33 unique app categories present in our dataset. Family and Game apps have the highest market prevalence. Interestingly, Tools, Business and Medical apps are also at the top.


