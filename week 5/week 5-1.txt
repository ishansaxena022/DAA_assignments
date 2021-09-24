#include <iostream>
using namespace std;

int main(){
    int n,i,t;
    cin>>t;            
    while(t--){
        cin>>n;        
        char arr[n];
        for(i=0;i<n;i++){
            cin>>arr[i];         
        }
        int f[26]={0};
        for(int i=0;i<n;i++){
            f[arr[i]-'a']++;
        }
        int max=0,c;
        for(int i=0;i<26;i++){
            if(f[i]>max){
                max=f[i];
                c=i;
            }
        }
        if(max>1)
            cout<<char('a'+c)<<" - "<<max<<endl;
        else
            cout<<" No Duplicates Present"<<endl;
    }
return 0;
}