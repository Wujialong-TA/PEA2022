# [2-1 很厲害的SymPy: 符號計算的體驗]

![image](https://user-images.githubusercontent.com/89715433/202058575-1e60de13-29d4-4660-97b4-008451577049.png)

#1101
!pip install sympy
import sympy # import symbol calculation module
user = 'JiaLong'


#1102
from sympy import *
init_printing() # The function init_printing() will enable LaTeX pretty printing in note


#1103
x, y, z = symbols("x y z")
expr = 3*x + 2*y - z
expr

![image](https://user-images.githubusercontent.com/89715433/202058639-5eaf83d3-07e7-4cfd-89b0-1863063f367c.png)



#1104 solve liner equations

x, y, z = symbols('x y z')
eql = Eq(3*x+2*y-z, 6)
eql

# Lab1-2 用Python學到國高中數學, #1
x, y, z = symbols('x y z')
eq2 = 2*x**2 + 3*x - 5
eq2

![image](https://user-images.githubusercontent.com/89715433/202058921-23771c03-2da1-4813-9ac5-7a63ce489f20.png)


Rational(3,4) + Rational(5,6)

Rational(3,4) * Rational(5,6)

Rational(3,4) / Rational(5,6)

Rational(3,4) - Rational(5,6)

a, b = symbols('a b')
a/b
![image](https://user-images.githubusercontent.com/89715433/202058967-fc226959-fa90-4f19-ba1d-6dceb52a6956.png)


a*b

a+b

a-b

![image](https://user-images.githubusercontent.com/89715433/202058983-4e24b910-dde2-4fbf-bb6a-60f8eeac5397.png)

#2010
for i in range(1,30):
 print(prime(i), end = ' > ')

#2020
sqrt(3)

#2021
sqrt(9)

#2022
sqrt(3)*sqrt(9)

#2023
pi

![image](https://user-images.githubusercontent.com/89715433/202059067-4813da79-7260-4268-9d64-f4b2172a56d7.png)

import math as m
m.pi

#2034
N(pi,5) # show digits

#2035
N(pi,3) #show digits

#2036
expr = pi + sqrt(2) * Rational(3,4) + 1
expr

![image](https://user-images.githubusercontent.com/89715433/202059098-09fb0d11-73c9-412c-88c1-30fda016a335.png)

#2037
expr.evalf(6) # Show 6 digits

#2042
from sympy.abc import p, q, xi, h
x, n, a= symbols('x n a')
(xi+p) / 3*a*sqrt(n-9)

#2043
gcd(18,81) #最大公因數

#2044
gcd(18*x**4, 81*x**2)

![image](https://user-images.githubusercontent.com/89715433/202059131-ededb2d9-9516-4261-a01c-23eb9c699b2d.png)

#2045
factor(18*x + 81)

#2046
expr = 18*x**4-81*x**2

#2047
expr = 18*x**4-81*x**2
expand(expr)

#2048
expr = (x*h**2-98*x**3-y**2/3*x)**(h-x-1)
expr

![image](https://user-images.githubusercontent.com/89715433/202059163-6faa7493-2395-47f1-b881-3fc2eae28d9c.png)

#2049
powsimp(x**a*y**a)

#2050
eqn = Eq(x+2, 0) # Example 3 in Lab 1
eqn

#2051
solve(eqn) # Solve x = ?

#2052
eqn = Eq(x**2 - 4*x - 12, 0)
eqn

#2053
solve(eqn) # Example 4 in Lab 1

![image](https://user-images.githubusercontent.com/89715433/202059211-9710a9b5-a585-48e9-bb02-dc3313991ac2.png)

#2054 # Example 5 in Lab 1
x, y, z= symbols('x y z')
eq1 = Eq(x+y-z, -2)
eq2 = Eq(x+z, 2)
eq3 = Eq(x-y+2*z, 5)
solve((eq1, eq2, eq3), (x, y, z))

#2056
A = Matrix([[2, 3, 4],[9, 8, 1],[9, 3, 3]])
A

#2057
A.col(0) # Show first column

![image](https://user-images.githubusercontent.com/89715433/202059237-2d44ba0b-5f53-4fb6-9a88-626e117c6249.png)

#2058
A.row(0).T # Show first row and rotate the matrix

#2059
B = A * 2
B
C = A*B # Example 10 in lab 1
A, B, C

![image](https://user-images.githubusercontent.com/89715433/202059547-345be889-4cb4-4632-afab-e4f862d95da6.png)

#2061
plot(2*x**2+3*x-5) #Example 1 in Lab 1

![image](https://user-images.githubusercontent.com/89715433/202059315-d99f232a-439f-45f7-869f-9483c59ef91a.png)

#2062
plot(-2*x**2+3*x-5) #Quiz 1 in Lab 1

![image](https://user-images.githubusercontent.com/89715433/202059424-fd752e94-44bc-4092-a127-c7a5bfe1bbd1.png)

#2063
plot((1/2*x+1/2), -2*x+3) #Example 2 in Lab 1

### Final Result
from datetime import datetime
today = datetime.now()
print('*** Done by %s at' % user,today, type(today))

![image](https://user-images.githubusercontent.com/89715433/202059368-8fba401b-98d5-4ac4-8fd3-68bf75a9d3c5.png)

#2201 繪製第一張折線圖
user = 'JiaLong'

import matplotlib.pyplot as plt

x = [1,2,3,4,5]
# 劃出顏色紅色、圓形錨點、虛線、粗細 2、資料點大小 6 的線條
plt.plot(x,color='r', marker='o', lineStyle='--', linewidth=2, markersize=6)
plt.show()

#2202 多組數據的折線圖
import matplotlib.pyplot as plt

x = [[1,2,3,4,5],[1,2,3,4,5]]
y = [[1,2,4,8,16],[1,2,3,4,5]]
plt.plot(x[0], y[0], 'ro-', x[1], y[1], 'go--') # 依序填入資料
plt.show()

#2203 繪製第一張散布圖
import matplotlib.pyplot as plt

x = [1,2,3,4,5,6,7,8,9,10]
y = [11,8,26,16,9,17,23,4,14,10]

plt.scatter(x,y)
plt.show()

#2204 散布圖 - 對應出指定的顏色
import matplotlib.pyplot as plt

x = [1,2,3,4,5,6,7,8,9,10]
y = [11,8,26,16,9,17,23,4,14,10]
size = [i*100 for i in y] # 放大資料點數據 100 倍，比較容易觀察尺寸
plt.scatter(x,y,s=size,c=size,cmap='Set1') # 使用 Set1 的 colormap
plt.show()

#2205 繪製第一張長條圖，import matplotlib.pyplot as plt

x = [1,2,3,4,5] # 水平資料點
h = [10,20,30,40,50] # 高度
plt.bar(x,h)
plt.show()

#2206 兩組數據的長條圖
import matplotlib.pyplot as plt
x = [1,2,3,4,5]
x2 = [0.8,1.8,2.8,3.8,4.8]
h = [10,20,30,40,50]
h2 = [20,10,40,50,30]
plt.bar(x,h,color='b',width=0.4, align='edge')
plt.bar(x2,h2,color='r',width=0.4)
plt.show()

#2207 繪製第一張圓餅圖
import matplotlib.pyplot as plt
x = [1,2,3,4,5]
plt.pie(x, radius=1.5, labels=x)
plt.show()

#2208 圓餅圖的內部百分比
import matplotlib.pyplot as plt
x = [1,2,3,4,5]
plt.pie(x,
        radius=1.5,
        labels=x,
        autopct='%.1f%%')   # %.1f%% 表示顯示小數點一位的浮點數，後方加上百分比符號
plt.show()

#2209 甜甜圈圖表
import matplotlib.pyplot as plt
x = [1,2,3,4,5]
plt.pie(x,
        radius=1.5,
        autopct='%.1f%%',
        textprops={'color':'w','weight':'bold','size':14},
        pctdistance=0.7,
        wedgeprops={'linewidth':3,'edgecolor':'w','width':1})
plt.show()

#2210 繪製更精緻的等高線圖
import matplotlib.pyplot as plt
import math
import numpy as np
x = np.linspace(-3, 3, 200)    
y = np.linspace(-3, 3, 200)   
z = [[(1 - x[i]/2 + x[i]*3 + y[j]*5) * math.exp(-x[i]**2 - y[j]**2) for i in range(200)] for j in range(200)]
lv = np.linspace(np.min(z), np.max(z), 20)  
plt.figure(figsize=(8,6))
plt.contour(x,y,z,levels=lv)
plt.show()


#2211 Numpy 階梯折線圖
from numpy import random
import matplotlib.pyplot as plt
x = range(0,10)                    # 產生 0～9 共十個數字
y = random.randint(100,1000,10)    # 產生 100～1000 隨機十個數字
plt.step(x,y)                      # 繪製階梯折線圖
plt.plot(x,y,'o--', color='grey',alpha=0.3)    # 繪製折線圖
plt.show()

#2212
import matplotlib.pyplot as plt
x = range(0,10)
y1 = [1,5,10,6,9,20,18,19,22,12]
y2 = [12,5,8,9,18,12,20,25,16,7]
y3 = [5,9,14,18,21,4,7,19,2,5]
fig, ax = plt.subplots(2,2)
fig.set_size_inches(12,8)
ax[0,0].stackplot(x,y1,y2,y3,baseline='zero')
ax[0,1].stackplot(x,y1,y2,y3,baseline='sym')
ax[1,0].stackplot(x,y1,y2,y3,baseline='wiggle')
ax[1,1].stackplot(x,y1,y2,y3,
                  labels=['y1','y2','y3'],
                  baseline='weighted_wiggle',
                  colors=['#f66','#0a4','#fa0'])
ax[1,1].legend(loc='lower left')
plt.show()


#2213
import matplotlib.pyplot as plt
x = range(0,5)
y1 = [2,8,3,12,6]
y2 = [12,3,7,11,4]
plt.bar(x, y1)
plt.bar(x, y2, bottom=y1)
plt.show()

#2214
import matplotlib.pyplot as plt
x = x = [math.radians(i*72) for i in range(5)]   # 由角度轉換成弧度
y = [7,8,5,12,6]
fig = plt.figure(figsize=(6,6))
plt.subplot(projection='polar')  # 設定 projection='polar' 表示極座標系統
# plt.subplot(polar=True)
plt.bar(x,y)
plt.show()

#2215

import matplotlib.pyplot as plt
x = range(10)
y = [7,8,5,12,6,10,19,13,5,9]
fig = plt.figure(figsize=(6,6))
plt.subplot(projection='polar')                  # 設定為極座標
plt.scatter(x,y,s=[i*100 for i in y],alpha=0.5)  # 繪製散布圖
plt.show()

#2216
import matplotlib.pyplot as plt
fig = plt.figure(figsize=(6,6))
ax = plt.subplot(projection='3d')
x = [2,4,6,8,10]
y1 = 10
y2 = 13
y3 = 16
z = 1
ax.bar3d(x,y1,z,dx=1,dy=1,dz=[5,4,3,2,1])
ax.bar3d(x,y2,z,dx=1,dy=1,dz=[1,2,3,2,1])
ax.bar3d(x,y3,z,dx=1,dy=1,dz=[1,4,3,2,4])
plt.show()


#2217
import matplotlib.pyplot as plt
import random
fig = plt.figure(figsize=(10,8))
ax = plt.subplot(projection='3d')
x1 = [random.randint(0,100) for i in range(5000)]
x2 = [random.randint(100,200) for i in range(5000)]
x3 = [random.randint(200,300) for i in range(5000)]
y = [random.randint(0,100) for i in range(5000)]
z = [random.randint(0,100) for i in range(5000)]
ax.scatter(x1,y,z,s=30,c=z,cmap='Reds')
ax.scatter(x2,y,z,s=30,c=z,cmap='Blues')
ax.scatter(x3,y,z,s=30,c=z,cmap='Greens')
plt.show()

