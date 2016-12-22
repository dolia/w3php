---
title: PHP实现冒泡排序
date: 2014/07/13 20:49:12
categories: php
tags: [php,算法,排序]
thumbnail: http://k.zol-img.com.cn/dcbbs/20246/a20245262_01000.jpg
banner: http://ohufr3344.bkt.clouddn.com/0FA39D3F-9FF4-4D16-B5E1-771A128D38F0.png
---
冒泡排序算法的运作如下：（从后往前）

* 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
* 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
* 针对所有的元素重复以上的步骤，除了最后一个。
* 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

![直观图](http://upload.wikimedia.org/wikipedia/commons/3/37/Bubble_sort_animation.gif)

```php
$numbers = [2,34,1123,6,334,223,34,442,949];

function bubbleSort($numbers){
    $length = count($numbers);
    for($i=0;$i<$length;$i++){
        for ($j=0;$j<$length-$i-1;$j++){
            if ($numbers[$j]>$numbers[$j+1]){
                $temp = $numbers[$j];
                $numbers[$j] = $numbers[$j+1];
                $numbers[$j+1] = $temp;
            }
        }
    }
    return $numbers;
}

print_r(bubbleSort($numbers));

```
输出的结果为
> Array  
> (  
>     [0] => 2  
>     [1] => 6  
>     [2] => 34  
>     [3] => 34  
>     [4] => 223  
>     [5] => 334  
>     [6] => 442  
>     [7] => 949  
>     [8] => 1123  
> )  