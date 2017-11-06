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

