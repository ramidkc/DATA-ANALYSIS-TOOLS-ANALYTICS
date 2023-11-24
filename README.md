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
## Functionality
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

