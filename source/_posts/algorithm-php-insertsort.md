---
title: PHP实现插入排序算法
date: 2012/07/13 20:49:12
categories: php
tags: [php,算法,排序]
thumbnail: http://img000.hc360.cn/g8/M05/D4/1C/wKhQt1NPW3uENLm3AAAAAJ7GMI8810.jpg
banner: http://ohufr3344.bkt.clouddn.com/7956F01D-46F8-4204-A60F-6F8FC70A908C.png
---

对于一个数组A[0..n-1]的排序，我们有很多方法可以实现，这次我们使用**插入排序**来实现一下。 

为了能更好的理解插入排序，我们举一个例子。比如军训时候，教官要把所有的同学按照身高排成一列走正步。这时候，教官可以这么做：

>1. 教官先随便挑出来一个同学站到操场中间，让其他同学则等在操场边上等待入队。
2. 教官命令一位等待的同学进入队列，让入该同学自己主动跟已经排好的队列中的同学进行对比身高，对比过后，找到比自己高的同学，站在TA的身后。
3. 教官重复步骤2，直至所有同学都进入队伍。

这样整体下来，队伍就会按照顺序排列下来。

对于等待入队的同学来说，他所要做的是，逐一对比已经在队伍中的同学身高，挑比自己高的同学站在后面，也就是插入比自己高，比自己低的同学的队伍中。



代码如下：

```php
$numbers = [2,34,1123,6,334,223,34,442,949];

function insertSort($numbers){

    $length = count($numbers);
    for ($i=0;$i<$length;$i++){
        $j = $i;
        $key = $numbers[$i];
        while($j>0&&$numbers[$j-1]>$key){
            $numbers[$j] = $numbers[$j-1];
            $j--;
        }
        $numbers[$j]=$key;
    }
    return $numbers;
}

print_r(insertSort($numbers));


```

最终输出结果

>Array
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
