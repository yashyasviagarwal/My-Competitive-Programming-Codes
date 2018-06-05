```

//@monsij
// Om Sai Ram
#include<bits/stdc++.h>
#define ll long long int
 
 
using namespace std;
 
int main()
{
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);
	
	//freopen("testcase.txt","r",stdin);
	//freopen("full1.txt","w",stdout);
	
	ll t,a,b,c,x,y,z;
	ll h,m,l;
	cin >> t;
	while(t--)
	{
		cin >> x>> y >> z >> a >> b >> c;
		ll val1 = (x+y+z)*a;
		vector<ll>f_ans;
		f_ans.push_back(val1);
		ll max_b  = 0;
		vector<ll>dat;
		dat.push_back(x);
		dat.push_back(y);
		dat.push_back(z);
		sort(dat.begin(), dat.end());
		ll sml = dat[0];
		ll medium = dat[1];
		ll lrg = dat[2];
		h=lrg;
		m = medium;
		l = sml;
		if(medium == sml)
		{
			if(medium != lrg)
			{
				ll a = dat[0]+dat[1];
				ll b = (x+y+z)/2;
				if(a < b)
					max_b = a;
				else if(a >= b)
					max_b = b;
			}
			else
			{
				
				max_b = (x+y+z)/2;
			}
		}
		else if(medium != sml)
		{
			if(medium != lrg)
			{
				ll a = dat[0]+dat[1];
				ll b = (x+y+z)/2;
				if(a < b)
					max_b = a;
				else if(a >= b)
					max_b = b;
			}
			else
			{
				
				max_b = (x+y+z)/2;
			}
		}
		else
		{
			max_b = (x+y+z)/2;
		}
		
		ll max_c = dat[0];
		//////////////////////////
 
		ll r = 1 * b + ((x+y+z)-(2*1))*a;
		f_ans.push_back(r);
		r = max_b * b + ((x+y+z)-(2*max_b))*a;
		f_ans.push_back(r);
		/////////////////////////////
		ll val3=-1;
		
		for(ll i=1; i<=max_c; i++)
		{
			vector<ll>dat;
			dat.push_back(x-i);
			dat.push_back(y-i);
			dat.push_back(z-i);
			sort(dat.begin(), dat.end());
			ll sml = dat[0];
			ll medium = dat[1];
			ll lrg = dat[2];
			
			if(medium == sml)
			{
				if(medium != lrg)
				{
					ll a = dat[0]+dat[1];
					ll b = (x+y+z-(3*i))/2;
					if(a < b)
						max_b = a;
					else if(a >= b)
						max_b = b;
				}
				else
				{	
					
					max_b = (x+y+z-(3*i))/2;
				}	
			}
			else if(medium != sml)
			{
				if(medium != lrg)
				{
					ll a = dat[0]+dat[1];
					ll b = (x+y+z-(3*i))/2;
					if(a < b)
						max_b = a;
					else if(a >= b)
						max_b = b;
				}
				else
				{
				
					max_b = (x+y+z-(3*i))/2;
				}
			}
			else
			{
				
				max_b = (x+y+z-(3*i))/2;
			}
			
			for(ll j=0; j<=max_b; j++)
			{
				
				
					ll r = (i * c) + (j*b) + ((x+y+z)-(3*i)-(2*j))*a;
					f_ans.push_back(r);
					
					if(j==max_b)break;
					j = max_b-1;
	
			}
			if(i==max_c)break;
			i = max_c-1;
		}
		
		
		
		
		ll i = abs(h- (m+l));
		//cout << i << "\n";
		if(i <= l )
		{
		
		vector<ll>dat1;
		dat1.push_back(x-i);
		dat1.push_back(y-i);
		dat1.push_back(z-i);
		sort(dat1.begin(), dat1.end());
		ll sml1 = dat1[0];
		ll medium1 = dat1[1];
		ll lrg1 = dat1[2];
 
		if(medium1 == sml1)
		{
			if(medium1 != lrg1)
			{
				ll a = dat1[0]+dat1[1];
				ll b = (x+y+z-(3*i))/2;
				if(a < b)
					max_b = a;
				else if(a >= b)
					max_b = b;
			}
			else
			{	
				
				max_b = (x+y+z-(3*i))/2;
			}	
		}
		else if(medium1 != sml1)
		{
			if(medium1 != lrg1)
			{
				ll a = dat1[0]+dat1[1];
				ll b = (x+y+z-(3*i))/2;
				if(a < b)
					max_b = a;
				else if(a >= b)
					max_b = b;
			}
			else
			{
				
				max_b = (x+y+z-(3*i))/2;
			}
		}
		else
		{
			
			max_b = (x+y+z-(3*i))/2;
		}
		for(ll j=0; j<=max_b; j++)
		{
			ll r = (i * c) + (j*b) + ((x+y+z)-(3*i)-(2*j))*a;
			f_ans.push_back(r);
					
			if(j==max_b)break;
			j = max_b-1;
		}
		
		}
		sort(f_ans.begin(),f_ans.end());
		//for(ll i=0; i<f_ans.size(); i++)
			//cout << f_ans[i] << " ";
		cout << f_ans[0] << "\n";
	}
	return 0;
}
   
   
   
```


