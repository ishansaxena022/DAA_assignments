#include <iostream>
using namespace std;

void swap(int* a,int* b) {
    int temp=*a;
    *a=*b;
    *b=temp;
}

int partition(int arr[],int l,int high) {
    int piv=arr[high],i=l;
    for (int j=l;j<=high-1;j++) {
        if (arr[j]<=piv) {
            swap(&arr[i], &arr[j]);
            i++;
        }
    }
    swap(&arr[i], &arr[high]);
    return i;
}
int funct(int arr[],int l,int high,int k) {
    if (k>0 && k<=high-l+1) {
        int pos=partition(arr,l,high);
        if (pos-l==k-1)
            return arr[pos];
        else if (pos-l>k-1)
            return funct(arr,l,pos-1,k);
        else
        return funct(arr,pos+1,high,k-pos+l-1);
    }
    return -1;
}

int main(){
    int n,i,t,k;
    cin>>t;
    while(t--){
        cin>>n;
        int arr[n];
        for(i=0;i<n;i++){
            cin>>arr[i];
        }
        cin>>k;
        cout<<funct(arr,0,n-1,k)<<endl;
    }
    return 0;
}