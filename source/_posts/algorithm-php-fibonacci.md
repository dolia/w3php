---
title: PHP使用递归实现斐波那契数列
date: 2014/08/12 22:49:12
categories: php
tags: [php,算法]
thumbnail: http://www.lxkj.cc/upload/ck/images/20151026151208.JPG
banner: http://ohufr3344.bkt.clouddn.com/C8BB2641-0023-4580-AE07-2E5E7ABCB195.png
---

## 引言 ##

斐波那契数列又因数学家列昂纳多·斐波那契以兔子繁殖为例子而引入，故又称为“兔子数列”。

>一般而言，兔子在出生两个月后，就有繁殖能力，一对兔子每个月能生出一对小兔子来。如果所有兔子都不死，那么一年以后可以繁殖多少对兔子？


## 定义 ##

**斐波那契数列** 指的是这样一个数列 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233，377，610，987，1597，2584，4181，6765，10946，17711，28657，46368........

这个数列从第3项开始，每一项都等于前两项之和。

## 递推公式 ##

斐波那契数列：1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ...
如果设F(n）为该数列的第n项（n∈N*），那么这句话可以写成如下形式：:F(n)=F(n-1)+F(n-2)
显然这是一个线性递推数列。


![示意图](http://chuantu.biz/t5/44/1481099435x1973338723.gif)

下面我们使用PHP来是解决引言中提到的一年后可以繁殖多少兔子的问题。

```php

function fibonacci($n){

    if ($n<=2){
        return 1;

    }else{
        return fibonacci($n-1)+fibonacci($n-2);
    }

}

echo fibonacci(12);

//输出 144


```