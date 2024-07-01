# import
import yfinance as yf
import pandas as pd
import matplotlib.pyplot as plt
# 获取股票信息
symbol = "039610.KQ"
start_date = "2023-01-01"
end_date = "2024-01-01"
data = yf.download(symbol, start=start_date, end=end_date)
print(data.head)
# 简单的数据分析
print(data.describe())
# 绘制走势图
data['Close'].plot(figsize=(10, 6), label=symbol)
plt.title(f"{symbol}Stock Price")
plt.xlabel("Date")
plt.ylabel("Price")
plt.legend()
plt.show()
