#include<iostream>
using namespace std;
void insertion_sort(int arr[],int n){
	int c = 0;
	for(int i=1; i<n; i++){
		int key = arr[i];
		int j = i-1;
		while(j>=0 && arr[j]>key)
		{
			arr[j+1] = arr[j];
			j = j-1;
			c++;
		}
		arr[j+1] = key;
	}
	for(int i=0; i<n; i++){
		cout<<arr[i]<<" ";
	}
	cout<<endl;
	cout<<"Comparisons = "<<c<<endl;
	cout<<"shifts = "<<c+(n-1)<<endl;
	
}
int main(){
	int t;
	cin>>t;
	while(t--){
		int n;
		cout<<"Enter the size of the array: ";
		cin>>n;
		int arr[n];
		for(int i=0; i<n; i++){
			cin>>arr[i];
		}
		insertion_sort(arr,n);
		
	}
}