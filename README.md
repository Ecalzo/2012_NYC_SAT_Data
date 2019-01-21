# 2012 NYC SAT Data
Charts based on the publicly available NYC 2012 SAT data

Source: https://data.cityofnewyork.us/Education/2012-SAT-Results/f9bf-2cp4

Thanks to NYC open data!

![Chart](https://github.com/Ecalzo/2012_NYC_SAT_Data/blob/master/SAT_NYC.png)

### Code
This project was a great opportunity to learn about least squares regression and to play around with the manual implementation
and python's built-in implementation. Below I compare the two:

```python

'''
Some stats practice
Line of best fit - least squares regression
'''
n = df['boro'].count()
df_xy = df[x]*df[y]
df_x2 = df[x]**2
m = (n*df_xy.sum()-(df[x].sum())*(df[y].sum()))/((n*df_x2.sum())-((df[x].sum())**2))
b = (df[y].sum()-m*df[x].sum())/n
df['fx'] = m*df[x]+b
df.plot(x=x,y='fx',ax=axes[0], kind='line', style=[':'], alpha=0.3)

# we can also use the stats linregress function and get more data than we need!

m2, b2, r, p, se = stats.linregress(df_middle[x],df_middle[y])
df_middle['fx2']=m2*df_middle[x]+b2
df_middle.plot(x=x, y='fx2', ax=axes[1], kind='line', style=[':'], alpha=0.3, legend=False)

'''
end of stats practice
'''

```
