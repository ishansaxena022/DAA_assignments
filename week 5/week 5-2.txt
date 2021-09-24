#include<iostream>
#include <algorithm>
using namespace std;

int main(){
    int n,i,t,k;
    cout<<" Enter number of test cases: ";
    cin>>t;
    while(t--){
        cout<<"Enter size of the array: ";
        cin>>n;
        int arr[n];
        cout<<"Enter elements of the array: ";
        for(i=0;i<n;i++){
            cin>>arr[i];
        }
        cout<<"Enter key: ";
        cin>>k;
        sort(arr,arr+n);
        int l=0,r=n-1,f=0;
        cout<<"Elements whose sum is equal to the key: ";
        while(l<r){
            if(arr[l]+arr[r]==k){
                cout<<arr[l]<<" "<< arr[r];
                r--;
                f=1;
            }
            else if (arr[l]+arr[r]<k)
                l++;
            else
                r--;
        }
        if(f==0)
            cout<<"\nNo such pair exist"<<endl;
    }
    return 0;
}