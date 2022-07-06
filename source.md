Task 1: Import the data, drop duplicate rows, and inspect the data.
```# Read in dataset
import pandas as pd
apps_with_duplicates = pd.read_csv('datasets/googleplaystore.csv')

# Drop duplicates from apps_with_duplicates
apps = apps_with_duplicates.drop_duplicates()

# Print the total number of apps
print('Total number of apps in the dataset = ', apps.count())

# Have a look at a random sample of 5 rows
print(apps.sample(5))```

Task 2: Clean the dataset.

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
print(apps.info())```

Task 3:
