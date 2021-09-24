#include <iostream>
using namespace std;

int s=0,c=0;
void swap(int* a,int* b) {
    s++;
    int temp=*a;
    *a=*b;
    *b=temp;
}

int partition (int arr[], int l, int high) {
    int p1=arr[high];
    int i=(l-1);
    for (int j=l;j<=high-1;j++) {
        c++;
        if (arr[j]<p1) {
            i++;
            swap(&arr[i],&arr[j]);
        }
    }
    swap(&arr[i+1],&arr[high]);
    return (i+1);
}

void quickSort(int arr[],int l,int high) {
    if (l<high) {
        int piv = partition(arr,l,high);
        quickSort(arr,l,piv-1);
        quickSort(arr,piv+1,high);
    }
}

int main(){
    int n,i,t;
    cin>>t;
    while(t--){
        cin>>n;
        int arr[n];
        for(i=0;i<n;i++){
            cin>>arr[i];
        }
        quickSort(arr,0,n-1);
        for(int i=0;i<n;i++){
            cout<<arr[i]<<" ";
        }
        cout<<"\nComparisons: "<<c<<endl;
        cout<<"Swaps: "<<s<<endl;
        s=0;c=0;
    }
    return 0;
}