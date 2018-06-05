```

#include<bits/stdc++.h>
#define ll long long int
 
using namespace std;
 
int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	//freopen("input.txt","r",stdin);
    //freopen("output.txt","w",stdout);
    string str;
    int flag=0;
    ll ta_c,tb_c;
    //cin.ignore();
    while(getline(cin,str))
    {
        //cout << str[0] << "-->" << str[1] << "\n";
        ta_c=0;
        tb_c=0;
        flag=0;
        for(ll i=1; i<=20; i++)
        {
        	if(i%2==1 && str[i-1]=='1')
        		++ta_c;
        	else if(i%2==0 && str[i-1]=='1')
        		++tb_c;
        	if(i<=10)
        	{
        		ll diff = abs(ta_c-tb_c);
        		if(ta_c < tb_c)
        		{
        			ll turns_left = 5 - ((i+1)/2);
					if(diff > turns_left)
					{
						cout << "TEAM-B" << " " << i << "\n";
						flag=1;
						break;
					}
				}
				else if(ta_c > tb_c)
				{
					ll turns_left = 5 - (i/2);
					if(diff > turns_left)
					{
						cout << "TEAM-A" << " " << i << "\n";
						flag=1;
						break;
					}
				}
			}
			else
			{
				if(i%2==0)
				{
					if(ta_c > tb_c)
					{
						cout << "TEAM-A" << " " << i << "\n";
						flag=1;
						break;
					}
					else if(ta_c < tb_c)
					{
						cout << "TEAM-B" << " " << i << "\n";
						flag=1;
						break;
					}
				}
			}
		}
		if(flag==0)
			cout << "TIE" << "\n";
	}
	//cout << "Moon" ;
    return 0;
} 


```

