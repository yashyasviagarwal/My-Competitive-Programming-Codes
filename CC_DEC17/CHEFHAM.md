```

//OM SAI RAM
//16457066
//@Monsijb
#include<bits/stdc++.h>
#define ll long long int
#define MAX 100003
using namespace std;
 
int main()
{
	ios_base::sync_with_stdio(false);;
	cin.tie(NULL);
	ll t,n;
	cin >> t;
	while(t--)
	{
		cin >> n;
		ll arr_A[MAX];
		map <ll,ll>kon_kitne_baar;
		map <ll,ll>swap_map;
		map<ll,ll>::iterator it;
		vector<ll>single_occ;
		vector<ll>double_occ;
		ll single_cnt=0;
		ll twice_cnt=0;
		for(ll i=0; i<n; i++)
		{
			cin >> arr_A[i];
			if(kon_kitne_baar[arr_A[i]]==0)
			{
				++kon_kitne_baar[arr_A[i]];
				++single_cnt;
			}
			else
			{
				++kon_kitne_baar[arr_A[i]];
				--single_cnt;
				++twice_cnt;
			}
		}
		
		for(it = kon_kitne_baar.begin(); it!=kon_kitne_baar.end(); it++)
		{
			if(it->second==2)
				double_occ.push_back(it->first);
			else
				single_occ.push_back(it->first);
		}
		
		//Cases :-(
		if(single_cnt == 0 && twice_cnt > 0)
		{
			for(ll i=0; i<twice_cnt-1; i++)
				swap_map[double_occ[i]]=double_occ[i+1];
			swap_map[double_occ[twice_cnt-1]]=double_occ[0];
			if(n!=2)
				cout << n << "\n";
			else
				cout << 0 << "\n";
			for(ll i=0; i<n; i++)
				cout << swap_map[arr_A[i]] << " ";
			cout << "\n";
		}
		else if(single_cnt > 0 && twice_cnt == 0)
		{
			for(ll i=0; i<single_cnt-1; i++)
				swap_map[single_occ[i]]=single_occ[i+1];
			swap_map[single_occ[single_cnt-1]]=single_occ[0];
			if(n!=1)
				cout << n << "\n";
			else
				cout << 0 << "\n";
			for(ll i=0; i<n; i++)
				cout << swap_map[arr_A[i]] << " ";
			cout << "\n";
		}
		else if(single_cnt == 1 && twice_cnt > 1)
		{
			// 5 6 6 7 7 here 5 6 6 is backed up in a previous case
			for(ll i=0; i<twice_cnt-1; i++)
				swap_map[double_occ[i]]=double_occ[i+1];
			swap_map[double_occ[twice_cnt-1]]=double_occ[0];
			cout << n << "\n";
			ll ch=0;
			ll last = twice_cnt -1;
			for(ll j=0; j<n; j++)
			{
				if(arr_A[j]==double_occ[twice_cnt-1] && ch==0)
				{
					cout << swap_map[arr_A[j]] << " ";
					ch=1;
				}
				else if(arr_A[j]==double_occ[twice_cnt-1] && ch==1)
					cout << single_occ[0] << " ";
				else if(arr_A[j]==single_occ[0])
					cout << swap_map[double_occ[twice_cnt-1]] << " ";
				else
					cout << swap_map[arr_A[j]] << " ";
			}
			cout << "\n";
		}
		else if(single_cnt > 1 && twice_cnt == 1)
		{
			// 4 5 7 8 8 here 4 8 8 is backed up in a previous case
			cout << n << "\n";
			for (ll j=0; j<single_cnt; j++)
			{
				if(j == single_cnt -2)
					swap_map[single_occ[j]]=double_occ[0];
				else if(j == single_cnt -1)
					swap_map[single_occ[j]]=double_occ[0];
				else
					swap_map[single_occ[j]]=single_occ[j+2];
			}
			ll ch = 0;
			for (ll j=0; j<n; j++)
			{
				if(arr_A[j]==double_occ[0] && ch==0)
				{
					cout << single_occ[0] << " ";
					ch=1;
				}
				else if(arr_A[j]==double_occ[0] && ch==1)
					cout << single_occ[1] << " ";
				else
					cout << swap_map[arr_A[j]] << " ";
			}
			cout << "\n";
		}
		else if(single_cnt==1 && twice_cnt==1)
		{
			//1 1 2 here's the case
			cout << 2 << "\n";
			cout << arr_A[1] << " " << arr_A[2] << " " << arr_A[0] << "\n";
		}
		else
		{
			cout << n << "\n";
			for(ll i=0; i<single_cnt-1; i++)
				swap_map[single_occ[i]]=single_occ[i+1];
			swap_map[single_occ[single_cnt-1]]=single_occ[0];
			
			for(ll i=0; i<twice_cnt-1; i++)
				swap_map[double_occ[i]]=double_occ[i+1];
			swap_map[double_occ[twice_cnt-1]]=double_occ[0];
			
			for(ll i=0; i<n; i++)
				cout << swap_map[arr_A[i]] << " ";
			cout << "\n";
		}
		
	}
	return 0;
} 


```


