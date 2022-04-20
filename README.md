#include<stdio.h>

void accept(int *a,int n)
{
	int i;
	printf("\nenter the elements of array:");
	for(i=0;i<n;i++)
	{
		scanf("%d",&a[i]);
	}
}
 int bsearch(int *a,int lb,int ub,int x)
{
	int m;
	if(lb<=ub)
	{
		m=(lb+ub)/2;
		if(x==a[m])
		{
			return m;
		}
		else
		{
			if(x>a[m])
			{
				return bsearch(a,m+1,ub,x);
			}
			else
			{
				return bsearch(a,m-1,lb,x);
			}
		}
	}
	return -1;
 }
 main()
{
	int a[10],n,x,pos;
	printf("enter the no of elements:");
	scanf("%d",&n);
	accept(a,n);
	printf("enter the value to be search:");
	scanf("%d",&x);
	pos=bsearch(a,0,n-1,x);
	if(pos==-1)
	{
		printf("%d is not present",x);
	}
	else
	{
		printf("%d is present at %d position",x,pos+1);
	}
}


