# 
```
Numpy是科學計算庫,是一個強大的N維陣列物件ndarray，擁有廣播功能函數。可整合C/C++.fortran代碼的工具 ，更是Scipy、Pandas等的基礎
轉載自：https://www.cnblogs.com/TensorSense/p/6795995.html
```
```
.ndim ：維度 
.shape ：各維度的尺度 （2，5） 
.size ：元素的個數 10 
.dtype ：元素的類型 dtype(‘int32’) 
.itemsize ：每個元素的大小，以位元組為單位 ，每個元素占4個位元組 
```
## ndarray陣列的創建 
```
np.arange(n) ; 元素從0到n-1的ndarray類型 
np.ones(shape): 生成全1 
np.zeros((shape)， ddtype = np.int32) ： 生成int32型的全0 
np.full(shape, val): 生成全為val 
np.eye(n) : 生成單位矩陣

np.ones_like(a) : 按陣列a的形狀生成全1的陣列 
np.zeros_like(a): 同理 
np.full_like (a, val) : 同理

np.linspace（1,10,4）： 根據起止資料等間距地生成陣列 
np.linspace（1,10,4, endpoint = False）：endpoint 表示10是否作為生成的元素 
np.concatenate():
```
## 陣列的維度變換
```
.reshape(shape) : 不改變當前陣列，依shape生成 
.resize(shape) : 改變當前陣列，依shape生成 
.swapaxes(ax1, ax2) : 將兩個維度調換 
.flatten() : 對陣列進行降維，返回折疊後的一位元陣列
```
## 陣列的類型變換
```
資料類型的轉換 ：a.astype(new_type) : eg, a.astype (np.float) 
陣列向清單的轉換： a.tolist() 
```
## 陣列的索引和切片運算
```
一維陣列切片
a = np.array ([9, 8, 7, 6, 5, ]) 
a[1:4:2] –> array([8, 6]) ： a[起始編號：終止編號（不含）： 步長]

多維陣列索引
a = np.arange(24).reshape((2, 3, 4)) 
a[1, 2, 3] 表示 3個維度上的編號， 各個維度的編號用逗號分隔

多維陣列切片
a [：，：，：：2 ] 缺省時，表示從第0個元素開始，到最後一個元素 
```
## 陣列的運算 
```
np.abs(a) np.fabs(a) : 取各元素的絕對值 
np.sqrt(a) : 計算各元素的平方根 
np.square(a): 計算各元素的平方 
np.log(a) np.log10(a) np.log2(a) : 計算各元素的自然對數、10、2為底的對數 
np.ceil(a) np.floor(a) : 計算各元素的ceiling 值， floor值（ceiling向上取整，floor向下取整） 
np.rint(a) : 各元素 四捨五入 
np.modf(a) : 將陣列各元素的小數和整數部分以兩個獨立陣列形式返回 
np.exp(a) : 計算各元素的指數值 
np.sign(a) : 計算各元素的符號值 1（+），0，-1（-） 

np.maximum(a, b) np.fmax() : 比較（或者計算）元素級的最大值 
np.minimum(a, b) np.fmin() : 取最小值 
np.mod(a, b) : 元素級的模運算 
np.copysign(a, b) : 將b中各元素的符號賦值給陣列a的對應元素
```
## 資料的CSV檔存取
```
CSV (Comma-Separated Value,逗號分隔值) 只能存儲一維和二維陣列

np.savetxt(frame, array, fmt=’% .18e’, delimiter = None): 

frame是檔、字串等，可以是.gz .bz2的壓縮檔； 
array 表示存入的陣列； 
fmt 表示元素的格式 eg： %d % .2f % .18e ; 
delimiter： 分割字串，預設是空格 

eg： np.savetxt(‘a.csv’, a, fmt=%d, delimiter = ‘,’ )
```
```
np.loadtxt(frame, dtype=np.float, delimiter = None, unpack = False) : 
frame是檔、字串等，可以是.gz .bz2的壓縮檔； 
dtype：資料類型，讀取的資料以此類型存儲； 
delimiter: 分割字串，預設是空格; 
unpack: 如果為True， 讀入屬性將分別寫入不同變數。
```
```
多維資料的存取 
a.tofile(frame, sep=’’, format=’%s’ ) : frame: 檔、字串； sep: 資料分割字串，如果是空串，寫入檔為二進位 ； format:： 寫入資料的格式 
eg: a = np.arange(100).reshape(5, 10, 2) 
a.tofile(“b.dat”, sep=”,”, format=’%d’)

np.fromfile(frame, dtype = float, count=-1, sep=’’)： frame： 檔、字串 ； dtype： 讀取的資料以此類型存儲； count：讀入元素個數， -1表示讀入整個檔； sep: 資料分割字串，如果是空串，寫入檔為二進位

PS: a.tofile() 和np.fromfile（）要配合使用，要知道資料的類型和維度。

np.save(frame, array) : frame: 檔案名，以.npy為副檔名，壓縮副檔名為.npz ； array為陣列變數 
np.load(fname) : frame: 檔案名，以.npy為副檔名，壓縮副檔名為

np.save() 和np.load() 使用時，不用自己考慮資料類型和維度。
```
### numpy亂數函數
```
numpy 的random子庫

rand(d0, d1, …,dn) : 各元素是[0, 1）的浮點數，服從均勻分佈 
randn(d0, d1, …,dn)：標準正態分佈 
randint(low， high,（ shape）): 依shape創建隨機整數或整數陣列，範圍是[ low, high） 
seed(s) ： 亂數種子

shuffle(a) : 根據陣列a的第一軸進行隨機排列，改變陣列a 
permutation(a) : 根據陣列a的第一軸進行隨機排列， 但是不改變原陣列，將生成新陣列 
choice(a[, size, replace, p]) : 從一維陣列a中以概率p抽取元素， 形成size形狀新陣列，replace表示是否可以重用元素，預設為False。 
eg：  
replace = False時，選取過的元素將不會再選取

uniform(low, high, size) : 產生均勻分佈的陣列，起始值為low，high為結束值，size為形狀 
normal(loc, scale, size) : 產生正態分佈的陣列， loc為均值，scale為標準差，size為形狀 
poisson(lam, size) : 產生泊松分佈的陣列， lam隨機事件發生概率，size為形狀 
eg: a = np.random.uniform(0, 10, (3, 4)) a = np.random.normal(10, 5, (3, 4))
```
## numpy的統計函數
```
sum(a, axis = None) : 依給定軸axis計算陣列a相關元素之和，axis為整數或者元組 
mean(a, axis = None) : 同理，計算平均值 
average(a, axis =None, weights=None) : 依給定軸axis計算陣列a相關元素的加權平均值 
std（a, axis = None） ：同理，計算標準差 
var（a, axis = None）: 計算方差 
eg： np.mean(a, axis =1) ： 對陣列a的第二維度的資料進行求平均 
a = np.arange(15).reshape(3, 5) 
np.average(a, axis =0, weights =[10, 5, 1]) : 對a第一各維度加權求平均，weights中為權重，注意要和a的第一維匹配

min(a) max(a) : 計算陣列a的最小值和最大值 
argmin(a) argmax(a) : 計算陣列a的最小、最大值的下標（注：是一維的下標） 
unravel_index(index, shape) : 根據shape將一維下標index轉成多維下標 
ptp(a) : 計算陣列a最大值和最小值的差 
median(a) : 計算陣列a中元素的中位數（中值） 
eg：a = [[15, 14, 13], 
[12, 11, 10] ] 
np.argmax(a) –> 0 
np.unravel_index( np.argmax(a), a.shape) –> (0,0)
```
## numpy的梯度函數
```
np.gradient(a) ： 計算陣列a中元素的梯度，f為多維時，返回每個維度的梯度 
離散梯度： xy坐標軸連續三個x軸座標對應的y軸值：a, b, c 其中b的梯度是（c-a）/2 
而c的梯度是： (c-b)/1

當為二維陣列時，np.gradient(a) 得出兩個陣列，第一個陣列對應最外層維度的梯度，第二個陣列對應第二層維度的梯度。 

```
## 圖像的表示和變換
```
PIL， python image library 庫 
from PIL import Image 
Image是PIL庫中代表一個圖像的類（物件）

im = np.array(Image.open(“.jpg”))

im = Image.fromarray(b.astype(‘uint8’)) # 生成 
im.save(“路徑.jpg”) # 保存

im = np.array(Image.open(“.jpg”).convert(‘L’)) # convert(‘L’)表示轉為灰度圖

```



