#include<iostream>
using namespace std;
int main(){
    int t,i,n,key,c=0,j;
    cin>>t;  
    while(t--){
        cin>>n;
        int a[n];
        for(i=0;i<n;i++){
            cin>>a[i];   
        }
        cin>>key;       
        for(i=0;i<n;i++){
            if(a[i]==key){
                j=i;
                c=1;
                break;
            }
        }
        if(c==1){
            cout<<"\nPresent "<<j+1;
            cout<<"\n";
        }
        else{
            cout<<"\nNot Present "<<n;
        }
        cout<<"\n\n";
    }
return 0;
}