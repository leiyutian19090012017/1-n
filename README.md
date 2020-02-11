# 1-n
输入数字 n，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。

示例 1:

输入: n = 1
输出: [1,2,3,4,5,6,7,8,9]

 

说明：

    用返回一个整数列表来代替打印
    n 为正整数


void Print1ToMaxOfNDigits_2(int n)
{
	if (n <= 0)
	{
		printf("n必须为正整数，参数错误！");
		return;
	}
 
	char* number = new char[n + 1];
	number[n] = '\0';
 
	for (int i = 0; i < 10; i++)
	{
		number[0] = i + '0';//整数转为字符串
 
		Print1ToMaxOfNDigitsRecursively(number, n, 0);
	}
 
	delete[] number;
}
