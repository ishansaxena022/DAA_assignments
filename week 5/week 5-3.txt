#include<iostream>
using namespace std;
int main(){
	int m,n;
	cout<<" Enter size of 1st array: ";
	cin>>m;
	int arr2[m];
	cout<<" Enter the element of 1st array : ";
	for(int i=0; i<m; i++){
		cin>>arr2[i];
	}
	cout<<" Enter size of 2nd array : ";
	cin>>n;
	int arr[n];
	cout<<" Enter the element of 2nd array : ";
	for(int i=0; i<n; i++){
		cin>>arr[i];
	}
	int j=0, i=0;
	cout<<"\n Common element/s: ";
	while(i<m && j<n){
		if(arr2[i]>arr[j])
			j++;
		else if(arr2[i]<arr[j])
			i++;
		else if(arr2[i] == arr[j]){
			cout<<arr[j]<<" ";
			i++;
			j++;
		}
	}
cout<<"\n\n";
return 0;
}