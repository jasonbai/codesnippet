### 1.导入excel文件

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

file_name = "朝阳医院2016年销售数据.xlsx"

xls_file = pd.ExcelFile(file_name, dtype='object') # 统一先按照str读入，之后转换

table = xls_file.parse('Sheet1', dtype='object')

print type(xls_file)
print type(table)

table.head(10)
```

### 2. 数据基本观察

```python
print table.shape
print table.index
print table.columns
print table.info()
print table.count()
```

### 3.[数据列名-重命名](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.rename.html)

```python
col = {u'购药时间':'time',\
u'社保卡号':'cardno',\
u'商品编码':'drugId',\
u'商品名称':'drugName',\
u'销售数量':'saleNumber',\
u'应收金额':'virtualmoney',\
u'实收金额':'actualmoney'}
```

```python
table.rename(columns = col, inplace = True)	
```

```python
table.head()
```

### 4. [删除缺失值](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.dropna.html?highlight=dropna#pandas.DataFrame.dropna%7C)

```
dropna1 = table.dropna()
dropna2 = table.dropna(how = 'all') # 参数设定是，所有值为 NA 才删除掉

```



