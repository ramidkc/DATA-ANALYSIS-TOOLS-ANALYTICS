# DATA-ANALYSIS-TOOLS-ANALYTICS 
One Paragraph of project description goes here....

## Getting Started
Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

## Prerequisites
Python
pandas
sqlalchemy
pymysql (for MySQL connection

## Installing
Install the required packages
```
pip install sqlalchemy
pip install pymysql

```
## Usage
# Import Python Libraries
```
import pandas as pd
from sqlalchemy import create_engine
import pymysql
```
# Read CSV File

```
df = pd.read_csv("ramid\Documents\Durham\youtube_dataset.csv", encoding='latin-1')
```

# Functionality
# Calculate Channel Type Distribution

The code includes a function channeltype(data) to calculate the distribution of channel types from the top 1000 records of the dataset. The function returns a DataFrame with the 'channeltype', 'Count', and 'Percentage' columns.
```
def channeltype(data):
    top_1000 = data.iloc[0:1000]
    distribution = top_1000['channeltype'].value_counts( )
    percentage= distribution / len(top_1000) * 100
    result_table = pd.DataFrame({
        'channeltype': distribution.index,
        'Count': distribution.values,
        'Percentage': percentage.values
    })
    return result_table

```
## Save Top 1000 Records
The code extracts and saves the top 1000 records into a separate CSV file named top_1000_channels.csv. Additionally, it saves these records to a MySQL database table named top_1000_youtube_channels.

