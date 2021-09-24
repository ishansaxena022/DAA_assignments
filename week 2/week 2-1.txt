#include<iostream>
#include<unordered_map>
using namespace std;
int frequency(int arr[], int n, int number){
	unordered_map<int, int> m;
	for(int i=0; i<n; i++){
		if(m.count(arr[i])>0){
			m[arr[i]]++;
		}
		else
			m[arr[i]] = 1;
	}
	if(m.count(number)>0){
		return m[number];
	}
	return 0;
}
int main(){
	int t;
	cin>>t;
	while(t--){
		int n;
		cout<<"Enter the size of the array: "<<endl;
		cin>>n;
		int arr[n];
		cout<<"Enter the elements of array: "<<endl;
		for(int i=0; i<n; i++){
			cin>>arr[i];
		}
		int number;
		cin>>number;
		int ans = frequency(arr, n, number);
		if(ans == 0)
			cout<<"Key not present"<<endl;
		else
			cout<<number<<" - "<<ans<<endl;
	}
}