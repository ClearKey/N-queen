#include <bits/stdc++.h>
using namespace std;

int board[15],cnt=0,n;
int f(int i)
{
	for(int j=0;j<i;j++)
	{
		if(board[i]==board[j]||abs(board[i]-board[j])==(i-j))
			return 0;
	}
	return 1;
}
void nqueen(int i)
{
	if(i==n)
	{
		cnt++;
	}
	else
	{
		for(int j=0;j<n;j++)
		{
			board[i]=j;
			if(f(i))
			{
				nqueen(i+1);
			}
		}
	}
}
int main()
{
	cin>>n;
	nqueen(0);
	cout<<cnt;
}
