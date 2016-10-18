--- 
layout: default
title: small codes
category: interview
comments: true
---
# binary search
```C
/// finded return index of hit
/// or else return -1
int bin_serach(int A[],int n,int v)
{
	int b=0, e=n;
	int m=(b+e)/2;
	while (A[m]!=v && b!=e)
  	{
		if (v<A[m]) e=m;
		else b=m+1;
	}
	return b!=e? m :-1;
}
```
# quick sort
```C
/// b: close start, e: open start
void quick_sort(int A[], int b, int e)
{
	if (b >= e)
		return;
	int i = partition(A,b,e);
	quick_sort(A,b,i-1);
	quick_sort(A,i+1,e);
}
int partition(int A[], int b, int e)
{
	int v=A[e-1];
	/// from left
	while (b<e)
	{
		if (v >= A[b])
			b++;
		else {
			A[e]=A[b];
			e --;
			/// from right
			while (b<e)
			{
				if (v<=A[e-1])
					e --;
				else {
					A[b]=A[e-1];
					b++;
					break;
				}
			}
		}
	}
	return b;
}
```
