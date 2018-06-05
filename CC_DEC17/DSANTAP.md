```

Trivial solution 

//OM SAI RAM
//monsijb
#include<bits/stdc++.h>
#define ll long long int
 
using namespace std;
 
int main()
{
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);
	//freopen("input.txt","r",stdin);
	//freopen("output.txt","w",stdout);
	ll t;
	ll n,g,b,x,y;
	ll x_ord,y_ord,q,w;
	ll temp;
	cin >> t;
	while(t--)
	{
		cin >> n >> g >> b >> x >> y;
		ll present_volume[g];
		ll present_re[n];
		ll curr_present[n];
		for(ll i=0; i<g; i++)
		{
			cin >> present_volume[i];
		}
		for(ll i=0; i<n; i++)
		{
			cin >>x_ord >> y_ord >> curr_present[i] >> present_re[i];
		}
		for(ll i=n-1; i>=0; i--)
		{
			ll want_id = present_re[i];
			ll pick_up = curr_present[i];
			cout << 2 << " " << present_re[i] << "\n";
			cout << 1 << " " << i+1 << "\n";
			
			cout << 3 << " " << present_re[i] << "\n";
			cout << 2 << " " << curr_present[i] << "\n";
			if(i!=0)
			{
				cout << 1 << " " << 0 << "\n";
				cout << 3 << " " << curr_present[i] << "\n";
			}
		}
		cout << 1 << " " << 0 << "\n";
		cout << 0 << "\n";
	}
	return 0;
	
}


```

