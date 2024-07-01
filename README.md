# 介绍（introduction）
This aims at collecting hisotry data about price of a particular stock and visualising the data in form of line chart.
# 安装软件包（installing packages)
import yfinance as yf
/nimport matplotlib.pyplot as plt
# 获取股票信息 (collect stock price data)
symbol = "039610.KQ"
start_date = "2023-01-01"
end_date = "2024-01-01"
data = yf.download(symbol, start=start_date, end=end_date)
print(data.head)
print(data.describe())
# 绘制走势图 (form a line chart)
data['Close'].plot(figsize=(10, 6), label=symbol)
plt.title(f"{symbol}Stock Price")
plt.xlabel("Date")
plt.ylabel("Price")
plt.legend()
plt.show()
