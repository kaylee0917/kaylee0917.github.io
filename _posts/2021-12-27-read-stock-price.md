---
title: "Read Stock Price using Python 파이썬으로 미국 주식 가격 읽어보자"
layout: post
categories: [Python Programming]
---

#### Read Stock Price using Python 파이썬으로 미국 주식 가격 읽어보자

#### We are going to use pandas_datareader to pull stock price from Yahoo. Details are shown below:

- end: today's time
- start: 52 weeks ago from today's time
- ticker: AAPL, AMZN, and INTC tickers are used as an example
- price_df: dataframe with 2 columes. colume 1 has the name of stock and colume 2 has the current price for the corresponding stock.

#### pandas_datareader를 이용하여 Yahoo에서 미국 주식 가격을 읽어보도록 한다. 자세한 변수 설명은 밑에 나와 있다.

- end: 오늘 날짜/시각
- start: 오늘로 부터 52주 전의 날짜/시각
- ticker: AAPL, AMZN, and INTC 티커들이 예제로 사용됨
- price_df: 최종 데이터프레임이 저장되는 변수. 티커 이름은 colume 1에 'stock'이라는 이름으로 저장, 해당 티커 현재 가격은 colume 2에 'price'이라는 이름으로 저장됨.

* * * 

#### Python Code

```python code

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

df.to_excel('./stock_price.xlsx')
print(price_df)

```

#### Output

| |stock|price|
|------|---|---|
|0|AAPL|179.380005|
|1|AMZN|3384.020020|
|2|INTC|51.830002|

##### 문의사항
contact: fidly@naver.com
