---
title: "Read Stock Price using Python 파이썬으로 미국 주식 가격 읽기"
layout: post
categories: [Python Programming]
---

## 파이썬으로 미국 주식 가격을 읽어보자

코드는 간단하다. 아래의 코드를 살펴보자.

---

#### Python Code

```powershell
import datetime
import pandas as pd
from pandas_datareader import data as web

end = datetime.datetime.now()
start = end - datetime.timedelta(weeks=52)

current_price = []
ticker = ['AAPL', 'AMZN', 'INTC']

for k in range(len(ticker)):
    df = web.DataReader(ticker[k], 'yahoo', start, end)
    df = df.reset_index()
    current_price.append(float(df[df['Date'] == str(end.date())]['Adj Close']))
    
data = {'stock': ticker, 'price': current_price}
price_df = pd.DataFrame(data, columns=['stock', 'price'])
    
print(price_df)
```

#### Output
![image](https://user-images.githubusercontent.com/96516502/147637424-70470623-cd1d-4130-a3a9-569a6e4a01d4.png)
