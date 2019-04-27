#
```
https://docs.scipy.org/doc/numpy/reference/routines.linalg.html
```

# numpy實作手冊:使用numpy學習線性代數

```
完成底下
```
### dot運算
```
資料來源:
https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html#numpy.dot
```
```
np.dot(3, 4)

np.dot([2j, 3j], [2j, 3j])

a = [[1, 0], [0, 1]]
b = [[4, 1], [2, 2]]
np.dot(a, b)

a = np.arange(3*4*5*6).reshape((3,4,5,6))
b = np.arange(3*4*5*6)[::-1].reshape((5,4,6,3))

np.dot(a, b)[2,3,2,1,2,2]
sum(a[2,3,2,:] * b[1,2,:,2])
```

###
```
矩陣鏈乘積（英語：Matrix chain multiplication，或Matrix Chain Ordering Problem，MOCP）是可用動態規劃解決的最佳化問題。給定一序列矩陣，期望求出相乘這些矩陣的最有效方法。此問題並不是真的去執行其乘法，而只是決定執行乘法的順序而已。

因為矩陣乘法具有結合律，所有其運算順序有很多種選擇。換句話說，不論如何括號其乘積，最後結果都會是一樣的。例如，若有四個矩陣 {\displaystyle A} A、 {\displaystyle B} B、 {\displaystyle C} C和 {\displaystyle D} D，將可以有：

{\displaystyle ABCD=(AB)(CD)=A(BCD)=A(BC)D=...} {\displaystyle ABCD=(AB)(CD)=A(BCD)=A(BC)D=...}

但括號其乘積的順序是會影響到需計算乘積所需簡單算術運算的數目，即其效率。例如，設 {\displaystyle A} A為一 {\displaystyle 10\times 30} {\displaystyle 10\times 30}矩陣， {\displaystyle B} B為 {\displaystyle 30\times 5} {\displaystyle 30\times 5}矩陣與 {\displaystyle C} C為 {\displaystyle 5\times 60} {\displaystyle 5\times 60}矩陣，則：

{\displaystyle (AB)C} {\displaystyle (AB)C}有 {\displaystyle (10\times 30\times 5)+(10\times 5\times 60)=1500+3000=4500} {\displaystyle (10\times 30\times 5)+(10\times 5\times 60)=1500+3000=4500}個運算
{\displaystyle A(BC)} {\displaystyle A(BC)}有 {\displaystyle (30\times 5\times 60)+(10\times 30\times 60)=9000+18000=27000} {\displaystyle (30\times 5\times 60)+(10\times 30\times 60)=9000+18000=27000}個運算
明顯地，第一種方式要有效多了。既然已確認過此問題了，那要如何決定n個矩陣相乘的最佳順序呢？可以比較每一順序的運算量（使用蠻力），但這將需要時間O(2n)，是一種非常慢且對大n不實在的方法。那解決方法，如我們將看到的，是將問題分成一套相關的子問題。以解答子問題一次而再使用其解答數次，即可以徹底地得出其所需時間。此一方法稱為動態規劃。

```
```
from numpy.linalg import multi_dot

# Prepare some data
A = np.random.random(10000, 100)
B = np.random.random(100, 1000)
C = np.random.random(1000, 5)
D = np.random.random(5, 333)

# the actual dot multiplication
multi_dot([A, B, C, D])
```
