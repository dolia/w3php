---
title: PHP实现选择排序
date: 2015/08/12 22:49:12
categories: php
tags: [php,算法,排序]
thumbnail: http://ohufr3344.bkt.clouddn.com/CB77E21E-CE0C-4E09-86FD-B04D21777B12.png
banner: http://ohufr3344.bkt.clouddn.com/CB77E21E-CE0C-4E09-86FD-B04D21777B12.png
---

## 简介  ##
**选择排序**（Selection sort）是一种简单直观的排序算法。它的工作原理是每一次从待排序的数据元素中选出最小（或最大）的一个元素，存放在序列的起始位置，直到全部待排序的数据元素排完。

![效果图](http://upload.wikimedia.org/wikipedia/commons/b/b0/Selection_sort_animation.gif)

## 问题分析 ## 
在要排序的一组数中，选出最小（或者最大）的一个数与第1个位置的数交换；然后在剩下的数当中再找最小（或者最大）的与第2个位置的数交换，依次类推，直到第n-1个元素（倒数第二个数）和第n个元素（最后一个数）比较为止。

简单选择排序的示例：

 
![效果图](http://my.csdn.net/uploads/201207/18/1342586432_7130.jpg)

## 操作方法 ##

* 第一趟，从n 个记录中找出关键码最小的记录与第一个记录交换；

* 第二趟，从第二个记录开始的n-1 个记录中再选出关键码最小的记录与第二个记录交换；

* 以此类推.....

* 第i 趟，则从第i 个记录开始的n-i+1 个记录中选出关键码最小的记录与第i 个记录交换，直到整个序列按关键码有序。

 
 ## 代码示例 ##

 ```php
<?php

$numbers = [2,34,1123,6,334,223,34,442,949];


function selectSort($numbers){

    $length = count($numbers);


    for($i=0;$i<$length;$i++){

        $min = $i;

        for ($j=$i+1;$j<$length;$j++)
        {
            if ($numbers[$j]<$numbers[$min]){

                $min = $j;

            }
        }

        $temp = $numbers[$i];
        $numbers[$i] = $numbers[$min];
        $numbers[$min] = $temp;


    }

    return $numbers;

}

print_r( selectSort($numbers));

/**
 * 输出结果
 * (
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
 */



 ```