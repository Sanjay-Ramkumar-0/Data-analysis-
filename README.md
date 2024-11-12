# Data-analysis
# import
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# array using numpy
A = np.array([
    ['a', 'b', 'c'],
    ['d', 'e', 'f'],
    ['g', 'h', 'i']
])

print(A[:, :2])
a = np.arange(5)
a + 20
print(a)
# numpy
np.nan, nan means not a number
a = np.array([1, 2, 3, np.nan, np.nan, 4])
a.mean(), returns nan,as nan is like a virus everything it touches will become nan
no.inf, numpy supports infinite
np.isnan() and np.isinf() also take arrays as inputs, and return boolean arrays as results
np.isfinite()
df.dropna() will drop all the rows in which any null value is present
s.fillna(x) will fill NaN values with x in s dataframe.
s.fillna(method='ffill'),s.fillna(method='bfill'), fill=forward fill, bill='beyond fill')
# reading a csv file
df = pd.read_csv('file_name.csv',header=None)
df.columns=['col1_name','col2_name']
# pandas utility functions 
pd.isnull(np.nan)
pd.isnull(None)
pd.isna(np.nan)
pd.isna(None)
# creating series
certificates_earned = pd.Series(
    [8, 2, 5, 6],
    index=['Tom', 'Kris', 'Ahmad', 'Beau']
)

print(certificates_earned[certificates_earned > 5])
# create dataframe
sales = pd.DataFrame({'amazon':[100,200,300],'flipkart':[50,100,150]}, index = [2020,2021,2022])
sales['total'] = sales['amazon'] + sales ['flipkart']
# to know no of rows and columns in a dataframe
df.shape()
# to print first n rows and last n rows, by default n is 5
df.head(n)
df.tail(n)
# adding new column in dataframe
certificates_earned = pd.DataFrame({
    'Certificates': [8, 2, 5, 6],
    'Time (in months)': [16, 5, 9, 12]
})
names = ['Tom', 'Kris', 'Ahmad', 'Beau']

certificates_earned.index = names
longest_streak = pd.Series([13, 11, 9, 7], index=names)
certificates_earned['Longest streak'] = longest_streak

print(certificates_earned)

# changing index
certificates_earned = pd.DataFrame({
    'Certificates': [8, 2, 5, 6],
    'Time (in months)': [16, 5, 9, 12]
})

certificates_earned.index = ['Tom', 'Kris', 'Ahmad', 'Beau']
# printing graph
print(sales.plot(kind='scatter', x='total', y= 'index', figsize=(6,6))
print(sales['total'].plot(kind='hist', bins = 100, figsize = (14,6))
# loc, iloc is used for slicing 
print(sales.iloc(:,0))
print(sales.iloc([0,2],[0,2]))
print(sales.loc(:,['amazon']))




