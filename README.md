# Dataset used:Prisoners dataset sourced from data.gov.in
# 1. Data Loading
  # a. Load the dataset “prisoners.csv” using pandas and display the first and last five rows in the dataset.

    import pandas as pd
    prisoners_data = pd.read_csv('prisoners.csv')
    prisoners_data.head()

    prisoners_data.tail()

  # b. Use describe method in pandas and find out the number of columns. Can you say something about those rows who have zero inmates?

    # Describe prisoners data
        prisoners_data.describe()

    # Number of columns
        len(prisoners_data.columns) 

  # Rows with zero inmates
    # Change the variable name to remove spaces in between
      prisoners_data.columns = 'State_UT','Year','Elementary_Education','Adult_Education','Higher_Education','Computer_Course'
      
      prisoners_data.columns
      Index(['State_UT', 'Year', 'Elementary_Education', 'Adult_Education','Higher_Education', 'Computer_Course'],dtype='object')
      
    # States with Zero inmates
      prisoners_data.loc[(prisoners_data.Elementary_Education == 0) & (prisoners_data.Adult_Education == 0) 
                   & (prisoners_data.Higher_Education == 0) & (prisoners_data.Computer_Course == 0)]
