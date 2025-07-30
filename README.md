# DSA
#include <iostream>
#include<vector>
using namespace std;

class Max2
{
public:
	// 二分递归求最大值
	int max2(int a[], int left, int right)
	{
		if (left == right) // 只有一个元素
			return a[left];
		else if (left + 1 == right) // 只有两个元素
			return a[left] > a[right] ? a[left] : a[right];
		else // 多于两个元素
		{
			int mid = (left + right) / 2;
			int maxLeft = max2(a, left, mid);
			int maxRight = max2(a, mid + 1, right);
			return maxLeft > maxRight ? maxLeft : maxRight;
		}
	};
protected:
	int a[100];
};
