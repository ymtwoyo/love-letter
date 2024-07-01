# 介绍（introduction）
This aims at collecting hisotry data about price of a particular stock and visualising the data in form of line chart.
# 安装软件包（installing packages)
import yfinance as yf
import matplotlib.pyplot as plt
# 获取股票信息 (collect stock price data)
symbol = "039610.KQ"
start_date = "2023-01-01"
end_date = "2024-01-01"
data = yf.download(symbol, start=start_date, end=end_date)
print(data.head)
print(data.describe())

<bound method NDFrame.head of               
| Date | Open | High | Low | Close | Adj | Close | Volume |
| ---- | ---- | ---- | --- | ----- | --- | ----- | ----- |
|2023-01-02 | 4685.0 | 4705.0 | 4515.0 | 4540.0 | 4540.0 | 54808 |
|2023-01-03 | 4475.0 | 4595.0 | 4410.0 | 4585.0 | 4585.0 | 72002 |
|2023-01-04 | 4500.0 | 4750.0 | 4500.0 | 4700.0 | 4700.0 | 28167 |
|2023-01-05 | 4725.0 | 4825.0 | 4690.0 | 4720.0 | 4720.0 | 30856 |
|2023-01-06 | 4670.0 | 5130.0 | 4670.0 | 4775.0 | 4775.0 | 291978 |
| ... | ... | ... | ... | ... | ... | ... |
|2023-12-21 | 5480.0 | 5520.0 | 5450.0 | 5500.0 | 5500.0 | 23769 |
|2023-12-22 | 5490.0 | 5530.0 | 5430.0 | 5530.0 | 5530.0 | 22181 |
|2023-12-26 | 5530.0 | 5530.0 | 5420.0 | 5530.0 | 5530.0 | 16937 |
|2023-12-27 | 5530.0 | 5530.0 | 5450.0 | 5480.0 | 5480.0 | 10648 |
|2023-12-28 | 5490.0 | 5540.0 | 5480.0 | 5530.0 | 5530.0 | 21685 |

[244 rows x 6 columns]>

| name | Open | High | ... | Adj | Close | Volume |
| ---- | ---- | ---- | --- | --- | ----- | ------ |
count | 244.000000 | 244.000000 | ... |  244.000000 | 2.440000e+02 |
mean | 5634.754098 | 5732.254098 | ... | 5637.848361 | 2.534730e+05 |
std | 433.131649 | 458.966948 | ... | 425.147253 | 1.156648e+06 |
min | 4475.000000 | 4595.000000 | ... | 4540.000000 | 1.063300e+04 |
25% | 5400.000000 | 5497.500000 | ... | 5415.000000 | 3.315575e+04 |
50% | 5570.000000 | 5635.000000 | ... | 5570.000000 | 6.429800e+04 |
75% | 5770.000000 | 5862.500000 | ... | 5760.000000 | 1.317128e+05 |
max | 6780.000000 | 7050.000000 | ... | 6720.000000 | 1.218242e+07 |

[8 rows x 6 columns]

# 绘制走势图 (form a line chart)
data['Close'].plot(figsize=(10, 6), label=symbol)
plt.title(f"{symbol}Stock Price")
plt.xlabel("Date")
plt.ylabel("Price")
plt.legend()
plt.show()
