# m-ng-2-chi-u-t-m-c-t-c-s-fibonaci-l-n-nh-t-trong-ma-tr-n-trong-tr-ng-h-p-s-fibonaci-b-ng-nhau
mảng 2 chiều tìm cốt có số fibonaci lớn nhất  trong ma trận , trong trường hợp có nhiều cột số fibonaci bằng nhau thì in ra cột có tổng số fibonaci lớn nhất






#include <iostream>
#include <bits/stdc++.h>
#include <fstream>
#include <set>
#include <vector>
#include <algorithm>
using namespace std;
set <long long  > fibo;
void vb(){
	long long fb[94];
	fb[0]=0;
	fb[1]=1;
	for (int i=2;i<=93;i++){
		fb[i]=fb[i-1]+fb[i-2];
	}
	for (int i=0;i<=93;i++){
		fibo.insert(fb[i]);
	}
}
int main(){
vb();
int n,m;
cout<<" nhap n"; cin>>n;
cout<<" nhap m:"; cin>>m;
int a[n][m];
for (int i=0;i<n;i++){
	for (int j=0;j<m;j++){
		cin>>a[i][j];
	}
}
int ans,sum,cot;
for (int i=0;i<m;i++){
	int dem,tmp;
	for (int j=0;j<n;j++){
		if (fibo.count(a[j][i]) == 1){
			dem++;
			tmp+=a[j][i];	
		}
	
	}
	if(dem>ans){
		ans=dem;
		sum=tmp;
		cot=i;
	}
	 else if(dem==ans){
		if ( tmp>sum){
		sum=tmp;
		cot=i;
		}
	}
		
}
cout<<"cot:"<<cot;
for (int i=0;i<n;i++){
	cout<<a[i][cot];
}


    return 0;

}






