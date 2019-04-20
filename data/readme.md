# 此目錄放置常用的作業所需之data

## 讀取遠方資料集的方法

```
import csv
import urllib2
url='http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data'
response=urllib2.urlopen(url)
cr=csv.reader(response)
for rows in cr:
   print rows
```

## Mastering pandas教科書所使用的資料集
```
Mastering pandas
Femi Anthony
June 2015

https://www.packtpub.com/big-data-and-business-intelligence/mastering-pandas

https://github.com/femibyte/mastering_pandas
```

```
https://colab.research.google.com/drive/1D_a3idela6AvAMOm4AxigfoecY1YlQvm
```
