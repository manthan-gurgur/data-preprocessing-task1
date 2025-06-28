# data-preprocessing-task1
Cleaned and normalized twitter.csv dataset using Python
import pandas as pd
from sklearn.preprocessing import StandardScaler, LabelEncoder
data = pd.read_csv('/content/twitter.csv')  # Your uploaded file
data.head()  # See the first 5 rows
data = data.dropna()  # Remove rows with missing data
data.info()  # Check what columns and data types it has
encoder = LabelEncoder()
# Step 5: Select only number columns (longitude, latitude)
number_data = data[['longitude', 'latitude']]

# Normalize the data
scaler = StandardScaler()
scaled_data = scaler.fit_transform(number_data)

# Create a DataFrame from the scaled data
scaled_df = pd.DataFrame(scaled_data, columns=['longitude', 'latitude'])
scaled_df.head()
scaled_df.to_csv('cleaned_twitter.csv', index=False)
print("🎉 Task 1 complete! Cleaned data saved as cleaned_twitter.csv")


