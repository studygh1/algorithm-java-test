
## 快速排序

快速排序也是交换排序的一种，是对冒泡排序的改进，是目前所有排序方法中速度最快的一种。
在冒泡排序中，记录的比较和交换是在相邻两个单元中进行的，记录每次的交换只能上移或下移一个相邻位置，因而总的比较次数和移动次数比较多；
而在快速排序中，记录的比较和移动从两段向中间进行，关键字大的记录一次就能交换到后面单元，关键字较小的记录一次就能交换到前面单元，记录每次移动的距离比较远，因而总的比较次数和移动次数比较少。

快速排序的基本思想是：在待排序的n个记录中任意选择一个记录作为标准记录（通常选第1个记录作为标准记录），以该记录的关键字为基准，将当前的无序区划分为左右两个较小的无序子区，
是左边无序子区中各记录的关键字均小于基准记录的关键字，使右边无序子区中各记录的关键字均大于或等于基准记录的关键字，而标准记录则位于两个无序子区的中间位置
（也就是该记录最终排序的位置），分别对左、右两个无序子区继续进行上述的划分过程，直到无序子区中所有的记录都排好序为止。
在快速排序中，将待排序区间按照标准记录关键字分为左、右两个无序子区的过程称为一趟快速排序（或一次划分）。

一趟快速排序的具体做法是：

1. 将标准记录r[s]保存到临时变量temp中，temp=r[s]。
1. 另j从n向左扫描，将r[j]与temp进行比较，直到找到第一个满足temp>r[j]条件的记录时停止，然后将r[j]移到r[i]的位置。
1. 令i从i+1起向右扫描，将r[i]与temp比较，直到找到第一个满足temp<r[i]条件的记录时停止，然后将r[i]移到r[j]的位置。
1. 反复交替执行步骤②和步骤③，知道指针i和j指向同一个位置(即i=j)时为止，此时i就是标准记录temp最终存放的位置，因此将temp存放到r[i]单元就完成了一次划分过程。

至此，一趟快速排序过程完成，数组被分成r[s..i-1]和r[i+1..t]两个部分。