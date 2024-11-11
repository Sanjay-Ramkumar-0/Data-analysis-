# Data-analysis-
import pandas as pd
import 
sales = pd.DataFrame({'amazon':[100,200,300],'flipkart':[50,100,150]}, index = [2020,2021,2022])
sales['total'] = sales['amazon'] + sales ['flipkart']
print(sales.plot(kind='scatter', x='total', y= 'index', figsize=(6,6))
print(sales['total'].plot(kind='hist', bins = 100, figsize = (14,6))
# loc, iloc is used for slicing 
print(sales.iloc(:,0))
print(sales.iloc([0,2],[0,2]))
print(sales.loc(:,['amazon']))
A = np.array([
    ['a', 'b', 'c'],
    ['d', 'e', 'f'],
    ['g', 'h', 'i']
])

print(A[:, :2])


