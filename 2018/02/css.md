### 1. W3C盒模型和IE盒模型

**关注width**

![](http://images.cnitblog.com/blog/347002/201409/121710262933336.jpg)
![](https://images2015.cnblogs.com/blog/964016/201607/964016-20160726110215294-2099215633.jpg)

### 2. :nth-child(odd) 与 :nth-child(even)

分别匹配序号为奇数与偶数的元素。奇数(odd)与(2n+1)结果一样；偶数(even)与(2n+0)及(2n)结果一样

### 3. table 边框合并

    border-collapse: collapse;  /* table的属性，collapse值表示把tr和td的border-spacing忽略，同等宽度下会优先使用td的border */
    
PS: border-spacing这个table的属性是设置tr和td的border之间的间距值，如果为0那么2条border就会无缝拼接

### 4. 关于文字换行

 1. 强制换行： 
 
 
        word-break:break-all; /* 连续英文强制换行 ,另外一个属性值keep-all	只能在半角空格或连字符处换行 */
        
        
        
