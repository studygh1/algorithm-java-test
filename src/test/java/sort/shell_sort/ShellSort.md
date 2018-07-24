
## 希尔排序

希尔排序又称缩小增量排序，较直接插入排序方法有了较大的改进。希尔排序的基本思想是：不断把待排序的记录分成若干个小组，然后对同一组内的记录进行排序。

希尔排序的过程如下：                
(1)以d1(0<d1<n-1)为步长（增量），把数组r中的n个元素分为d1个小组，将所有下标距离为d1的记录放在同一组中。                 
(2)对每组内的记录分别进行直接插入排序。这样一次分组排序过程称为一次排序。                  
(3)以d2(d1>d2)为步长（增量），重复上述步骤，知道di = 1，把所有n个元素放在一个组内，进行直接插入排序为止。该次排序结束，整个序列的排序工作完成。

在希尔排序中，增量序列的选取到目前为止尚未取得一个最佳值，但最后一次排序时的增量值必须为1。一般选取增量序列的规则是：取di+1为di/3~di/2之间的数，最简单的方法是取di+1=di/2。

【算法分析】

初始时，由于选取的间隔值比较大，各组内的记录比较少，所以组内排序就比较快。在以后的排序中，虽然各组中的记录个数增多，但是通过前面的多次排序，组内的记录越来越接近有序，所以组内的排序也比较快。

希尔排序的速度一般比插入排序要快，希尔排序的平均比较次数大致为O(n^1.3)，但是希尔排序的分析是一个非常复杂的事情，这是因为时间的复杂度依赖于所取的增量序列。希尔排序的空间复杂度为O(1)。

由于希尔排序是按增量分组进行排序的，所以希尔排序是一种不稳定的排序方法。

代码示例：
- [C语言版](https://github.com/lq920320/Hello-World/blob/master/shellSort.cpp)
- [Java版](https://github.com/lq920320/algorithm-java-test/blob/master/src/test/java/sort/shell_sort/ShellSortTest.java)

