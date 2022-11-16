
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

![image](https://user-images.githubusercontent.com/89715433/202092051-b7c9a567-888f-4108-a69e-54b0cba685a4.png)


from google.colab import drive
drive.mount('/content/drive')

%cd '/content/drive/MyDrive/PEA2022'

![image](https://user-images.githubusercontent.com/89715433/202092130-614168b7-8deb-4ec6-b22b-11455ee22a46.png)

df=pd.read_csv('sales/train.csv')  #相對路徑
df  #df.head()

# Lab 3-2 實戰時刻! Let’s fight!

![image](https://user-images.githubusercontent.com/89715433/202092307-0fd31890-4746-4d33-8dff-d7f68a4b65e1.png)

![image](https://user-images.githubusercontent.com/89715433/202092369-6d9e9a3d-69f3-4a6a-819f-daee0c005d14.png)


#3106 設定date日期作為索引，成為有時間序列的資料
#參數說明 parse_dates指定對date做日期序列解析
#index_col指定某一列作為索引
train = pd.read_csv('sales/train.csv', 
    parse_dates=['date'], index_col=['date'])
train #train.head()
#日期date(索引)、3欄數據:商店store、商品item、銷售額sales

![image](https://user-images.githubusercontent.com/89715433/202092398-30ed846a-47b9-44ec-b9b8-c4d233236824.png)

#3107 df.shape顯示數據量(913000x3)

train.shape #(913,000 筆資料, 3 欄位)


913000/30 #相當於3萬多頁的Excel表格


# 3117 只查單一產品item #1的銷售總額
df2=train.groupby(['item']).sum()
df2.loc[1]

# 計算各分店store之2013~2017 5年總銷售金額

# 91萬多筆資料(3萬頁)，用Execl要幾個步驟?做多久?

![image](https://user-images.githubusercontent.com/89715433/202092475-ae025a45-e886-4a5f-8162-6c5785e11689.png)

# 1. 對特定產品item求 銷售總額??
#1509
%%time
df2=train.groupby(['item']).sum()
print(df2.head(10))

![image](https://user-images.githubusercontent.com/89715433/202092526-5ff13af1-afde-42c1-bfec-5d7cca74df25.png)

# 2. 平均分店的銷售總額??
df3 = df2=train.sum()
print(df3)

print('Total Sales = ', df3['sales'])
print('AVG Sales = $%.1f' % (df3['sales']/10))

# 3. 品項太多，只查單一產品item #12的銷售總額
#1509a df.loc依照列名稱選定資料 ("12")
df2=train.groupby(['item']).sum()
df2.loc[12]


![image](https://user-images.githubusercontent.com/89715433/202092602-ecbd2df5-af11-4420-9e7f-b7938bb31980.png)

#1510 匯入Matplot(一般念法)
import matplotlib as mpl
import matplotlib.pyplot as plt
plt.style.use('classic') #設定主題配色 classic, ggplot, bmh


#1511 一行搞定，先分組`item`看`sales`金額
#使用groupby依照item分組(橫軸)，sum()值加總，plot.bar()繪柱狀圖，y='sales'縱軸，figsize=(10,4)出圖尺寸
#設定圖形尺寸 figsize=(10寬,4高) 單位英寸
train.groupby('item').sum().plot.bar(y='sales',figsize=(10,4))

![image](https://user-images.githubusercontent.com/89715433/202092648-2be6f2b5-1a3e-4609-9da1-5d8c75556999.png)

#分商店store繪製sales營業額圖表
train.groupby('store').sum().plot.bar(y='sales',figsize=(10,3))
