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
a = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])

print(np.full_like(a, 100))
[[100 100 100 100 100]
[100 100 100 100 100]]
# numpy
np.nan, nan means not a number
a = np.array([1, 2, 3, np.nan, np.nan, 4])
a.mean(), returns nan,as nan is like a virus everything it touches will become nan
no.inf, numpy supports infinite
np.isnan() and np.isinf() also take arrays as inputs, and return boolean arrays as results
np.isfinite()
df.dropna() will drop all the rows in which any null value is present
df.dropna(axis=1) will drop all the columns in which any null value is present
s.fillna(x) will fill NaN values with x in s dataframe.
df.dropna(how='all'), df.dropna(how='any') which is default
df.dropna(thresh=int) where int is any integers which acts as threshold value

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
# cleaning not null values in a dataframe
df = pd.DataFrame({
    'Sex': ['M', 'F', 'F', 'D', '?'],
    'Age': [29, 30, 24, 290, 25],
})
df['Sex'].unique()
df['Sex'].value_counts()
df['Sex'].replace('D', 'F')
df['Sex'].replace({'D': 'F', 'N': 'M'})
# duplicates in dataframe
ambassadors = pd.Series([
    'France',
    'United Kingdom',
    'United Kingdom',
    'Italy',
    'Germany',
    'Germany',
    'Germany',
], index=[
    'Gérard Araud',
    'Kim Darroch',
    'Peter Westmacott',
    'Armando Varricchio',
    'Peter Wittig',
    'Peter Ammon',
    'Klaus Scharioth '
])
duplicated (that will tell you which values are duplicates) and drop_duplicates (which will just get rid of duplicates)
ambassadors.duplicated(), if there are 2 same elements considers first as unique
ambassadors.duplicated(keep='last'), if there are 2 same elements considers last as unique
ambassadors.duplicated(keep=False), if there are 2 same elements considers both as unique
ambassadors.drop_duplicates()
ambassadors.drop_duplicates(keep='last')ambassadors.drop_duplicates(keep=False)
.drop_duplicates(subset=['Name'], keep='last')
# working on columns using pd
## spliting columns 
df = pd.DataFrame({
    'Data': [
        '1987_M_US _1',
        '1990?_M_UK_1',
        '1992_F_US_2',
        '1970?_M_   IT_1',
        '1985_F_I  T_2'
]})
df['Data'].str.split('_')
df = df['Data'].str.split('_', expand=True)
df.columns = ['Year', 'Sex', 'Country', 'No Children']
## regex in pandas
contains takes a regex/pattern
df['Country'].str.contains('U')
## replacing
df['Country'].str.replace(' ', '')
or
df['Country'].str.strip()
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




