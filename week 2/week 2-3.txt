#include<iostream>
using namespace std;
int main()
{
	int t;
	cin>>t;
	while(t--){
		int n;
		cin>>n;
		int arr[n];
		for(int i=0; i<n; i++){
			cin>>arr[i];
		}
		int number;
		cin>>number;
		int c=0;
		for(int i=0; i<n; i++){
			for(int j=0; j<n; j++){
				if(arr[i] - arr[j] == number)
					c++;
			}
		}
		cout<<c<<endl;
	}
	return 0;
}