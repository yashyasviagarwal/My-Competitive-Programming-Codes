```

//@Monsij
//CodeLiteV2.0
 
#include<bits/stdc++.h>
#define ll long long int
 
using namespace std;
 
int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    ll t,n,m;
    cin >> t;
    while(t--)
    {
        cin >> n >> m;
        string rep1="";
        string rep2="";
        for(ll i=0; i<m; i++)
        {
            if(i%2==0)
            {
                rep1+="R";
                rep2+="G";
            }
            else
            {
                rep1+="G";
                rep2+="R";
            }
        }
        string data[n];
        string sm1[n];
        string sm2[n];
        for(ll i=0; i<n; i++)
        {    
            cin >> data[i];
            if(i%2==0)
            {
                sm1[i]=rep1;
                sm2[i]=rep2;
            }
            else
            {
                sm1[i]=rep2;
                sm2[i]=rep1;
            }
        }
        ll cost1,cost2;
        cost1=0;
        cost2=0;
        ll r_to_g = 5;
        ll g_to_r = 3;
        for(ll i=0; i<n; i++)
        {
            for(ll j=0; j<m; j++)
            {
                if(data[i][j]!=sm1[i][j])
                {
                    if(data[i][j]=='R')
                        cost1 += r_to_g;
                    else
                        cost1 += g_to_r;
                }
                else if(data[i][j]!=sm2[i][j])
                {
                    if(data[i][j]=='R')
                            cost2 += r_to_g;
                    else
                            cost2 += g_to_r;
                }
            }
        }
        if(cost1 < cost2)
            cout << cost1 << "\n";
        else
            cout << cost2 << "\n";
    }
    return 0;
} 


```
