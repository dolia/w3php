---
title: PHP实现快速排序
date: 2015/12/12 22:49:12
categories: php
tags: 
	- php
	- 算法
	- 排序	
thumbnail: http://ohufr3344.bkt.clouddn.com/DFAACAA7-AFC2-4087-A6A5-C4A2F81D4594.png!thumb
banner: http://ohufr3344.bkt.clouddn.com/DFAACAA7-AFC2-4087-A6A5-C4A2F81D4594.png
---

## 算法简介 ##
快速排序（Quicksort）是对冒泡排序的一种改进。

快速排序由C. A. R. Hoare在1962年提出。它的基本思想是：通过一趟排序将要排序的数据分割成独立的两部分，其中一部分的所有数据都比另外一部分的所有数据都要小，然后再按此方法对这两部分数据分别进行快速排序，整个排序过程可以递归进行，以此达到整个数据变成有序序列。


![视觉感受](https://dn-linuxcn.qbox.me/data/attachment/album/201305/03/161701jmbrs6wkrgnzb6jc.gif)

## 问题分析 ##

设要排序的数组是A[0]……A[N-1]，首先任意选取一个数据（通常选用数组的第一个数）作为关键数据，然后将所有比它小的数都放到它前面，所有比它大的数都放到它后面，这个过程称为一趟快速排序。值得注意的是，快速排序不是一种稳定的排序算法，也就是说，多个相同的值的相对位置也许会在算法结束时产生变动。

## 操作方法  ##

一趟快速排序的算法是：
1. 设置两个变量i、j，排序开始的时候：i=0，j=N-1；
2. 以第一个数组元素作为关键数据，赋值给key，即key=A[0]；
3. 从j开始向前搜索，即由后开始向前搜索(j--)，找到第一个小于key的值A[j]，将A[j]和A[i]互换；
4. 从i开始向后搜索，即由前开始向后搜索(i++)，找到第一个大于key的A[i]，将A[i]和A[j]互换；
5. 重复第3、4步，直到i=j； (3,4步中，没找到符合条件的值，即3中A[j]不小于key,4中A[i]不大于key的时候改变j、i的值，使得j=j-1，i=i+1，直至找到为止。找到符合条件的值，进行交换的时候i， j指针位置不变。另外，i==j这一过程一定正好是i+或j-完成的时候，此时令循环结束）。


## 代码实现 ##

```php


$numbers = [2,34,1123,6,334,223,34,442,949];

function quickSort($numbers){

    if (!is_array($numbers)) return false;

    $length = count($numbers);

    if ($length<=1) return $numbers;



    $leftArr = $rightArr = [];

    for ($i=1;$i<$length;$i++){

        if ($numbers[$i]<$numbers[0]){


            $leftArr[] = $numbers[$i];
        }else{
            $rightArr[] = $numbers[$i];
        }

    }


    $leftArr = quickSort($leftArr);

    $rightArr = quickSort($rightArr);


    return array_merge($leftArr,[$numbers[0]],$rightArr);


}


print_r(quickSort($numbers));

/**
 *
 * 输出
 * Array
(
[0] => 2
[1] => 6
[2] => 34
[3] => 34
[4] => 223
[5] => 334
[6] => 442
[7] => 949
[8] => 1123
)

 *
 */


 ```



