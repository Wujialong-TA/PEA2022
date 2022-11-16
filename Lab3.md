
# 3-1 數據分析

![image](https://user-images.githubusercontent.com/89715433/202062550-2a4143f3-f3b0-4489-9d0b-0a14f81a5c7e.png)
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# random.randn(d0,  d1,  ...,  dn)
df = pd.DataFrame(np.random.randn(1000,  3), columns=list('ABC'))
df=df.cumsum()
df.plot(figsize=(20,5))
plt.show()

# 一行程式，快速取得台銀牌告匯率

![image](https://user-images.githubusercontent.com/89715433/202062755-3d36a4d6-0e08-4b94-aab0-4e50e0a3e964.png)

![image](https://user-images.githubusercontent.com/89715433/202062839-2ed97b22-99a5-4b2d-bb77-b1c6a5fb7e3e.png)


import datetime

df=pd.read_html('https://rate.bot.com.tw/xrt?Lang=zh-TW')[0] #台銀匯率
print(type(df))

td = datetime.datetime.today()
print(td)

#3103 行列結構資料表或試算表
df.head()

![image](https://user-images.githubusercontent.com/89715433/202062904-cab525f8-02a2-492c-a823-394f38fb4989.png)

from google.colab import drive
drive.mount('/content/drive')

%cd '/content/drive/MyDrive/PEA2022'



