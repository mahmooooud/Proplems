# 296A - Yaroslav and Permutations
#include <bits/stdc++.h>

using namespace std;
void solve(int A[],int n){
	sort(A,A+n);
	int P[1001] = {0};
	int i = 0;
	int c= 0;
	while(i<n){
		c = 1;
		while(i+1<n && A[i]==A[i+1]){
			c++;
			i++;
		}
		P[A[i]] = c;
		i++;
	}
	sort(P,P+1001);
	c = 0;
	for(i=0;i<1000;i++){
		c += P[i];
	}

	if(c>=P[1000]-1){
		cout<<"YES"<<endl;
	}
	else{
		cout<<"NO"<<endl;
	}
}

int main(){

	int n;
	cin>>n;
	int A[n];
	for(int i=0;i<n;i++){
		cin>>A[i];
	}
	solve(A,n);

	return 0;
}

