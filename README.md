# MBG6133_Final
*Relevant Jupyter Notebook file is uploaded to this Github Repository as* **ilkerkilic_mbg6133_final.ipynb**

## Q1
### Q1.1
First, we import the necessary libraries:
```
import numpy as np
import matplotlib.pylab as plt
```
Then we create the 100x100 array of random numbers that vary between [0,100]
```
a = np.random.randint(100, size=(100,100))
```
```
print(a)
a.shape
```
output:
```
[[69  1 92 ... 44 48 48]
 [45 14 56 ... 98 69 70]
 [77 17 78 ... 39 10 49]
 ...
 [31  1 24 ... 24 92 54]
 [ 9 25 23 ... 66 17 41]
 [80 68 13 ...  4 45 15]]

(100, 100)
```

### Q1.2

I used matplotlib (which i imported as plt) to plot a 2D heatmap:
```
plt.imshow(a)
```
output:

![heatmap1](https://user-images.githubusercontent.com/95715986/150211843-325bc2fc-6ca9-43a5-8fde-8ecc526ddf8f.png)

## Q2
### Q2.1
In order to filter out the odd numbers i used "%2 == 0" code to simply select the even numbers in the array, 
if the numbers are even it returns as "True", if not it returns as "False"
```
fltr_a = (a % 2 == 0)
```
```
print(fltr_a)
```
output:
```
[[False False  True ...  True  True  True]
 [False  True  True ...  True False  True]
 [False False  True ... False  True False]
 ...
 [False False  True ...  True  True  True]
 [False False False ...  True False False]
 [ True  True False ...  True False False]]
 ```
To see our filtered array (which has only the even numbers) i used: 
```
print(a[fltr_a])
```
output:
```
[92 60 44 ... 30 82  4]
```
Then to convert True/False statements into [0,1] values i used ".astype"
```
fltr_a_int = fltr_a.astype(int)
```
```
print(fltr_a_int)
fltr_a_int.shape
```
output:
```
[[0 0 1 ... 1 1 1]
 [0 1 1 ... 1 0 1]
 [0 0 1 ... 0 1 0]
 ...
 [0 0 1 ... 1 1 1]
 [0 0 0 ... 1 0 0]
 [1 1 0 ... 1 0 0]]

(100, 100)
```
### Q2.2
And finally, to plot the 2D heatmap of our new array:
```
plt.imshow(fltr_a_int)
```
output:

![heatmap2](https://user-images.githubusercontent.com/95715986/150214795-0d2b52d5-6cc8-49d0-89c5-078459282125.png)
