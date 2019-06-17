# 数据类型、变量、内存四区、指针
## 前言
1 写一个选择排序算法  
[选择排序算法](file1.c)  
出现的错误：error C2143: 语法错误 : 缺少“;”(在“类型”的前面)  
解决方法：  
```
	int a[] = {2,5,3,6,4};
	int n;
	n = sizeof(a)/sizeof(a[0]);//获得元素个数
	int i=0;
	int j=0;
	int temp=0;
```
c语言中注意要调整变量声明的位置，改为如下即可：  
```
	int a[] = {2,5,3,6,4};
	int n;
	int i=0;
	int j=0;
	int temp=0;
	n = sizeof(a)/sizeof(a[0]);//获得元素个数
```
2 对此算法进行函数封装  
[改进后程序](file2.c）  
对算法进行函数封装后，主程序语句变少，而且打印数组的时候只需调用函数print_array即可，不必使用for分别对排序前和排序后的数组进行输出了  
tips:数组形参退化为指针  
如果数组作为函数参数，数组形参退化为指针  
```
// 打印数组
/*
// 如果数组作为函数参数，数组形参退化为指针
// 下面四种写法都可以
// void print_array(int a[1], int n)
// void print_array(int a[], int n)
// void print_array(int *a, int n)
*/
void print_array(int a[10], int n)
{
	/*
	// 检验a是否为指针
	// n = sizeof(a)/sizeof(a[0]);//输出结果为1，因为此时a为指针，32位系统下占4个字节，64位占8个字节
	// 在主程序中的n则为5，因为彼时n是作为数组使用的
	*/
	int i = 0;
	for(i=0;i<n;i++)
	{
		printf("%d ",a[i]);
	}
	printf("\n");
}
```
## 数据类型（实质是固定内存大小的模具！）
1 基本类型（字节数）：  
 整形int（4）  
 浮点型float（4）、double（8）  
 字符型char（1）  
 空类型void  
2 结构类型（自定义类型）:数组（[]）结构（struct）类（class）联合（union）  
tips：数据类型只是模具，只有根据模具创建变量（实物）时，编译器才会分配内存空间  
dm
3 给变量起别名：typedef  
tips：1 typedef一种数据类型；2 配合结构体使用  
```
dm
```
4 void类型  
