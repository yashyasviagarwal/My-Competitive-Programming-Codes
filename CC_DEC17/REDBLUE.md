```

//@monsijb
//OM SAI RAM
#include<bits/stdc++.h>
#define ll long long int
#define limit 100 //no.of times to work with random numbers
 
using namespace std;
 
ll ans = INT_MAX;
 
void calculate_line(ll x1,ll y1,ll x2, ll y2,vector< pair<ll,ll> >red_p,vector< pair<ll,ll> >blue_p)
{
	double p1 = x1;
	double q1 = y1;
	double p2 = x2;
	double q2 = y2;
	double m_slope = (q2-q1)/(p2-p1);
	//cout << m_slope;
	ll ru,rd,bu,bd;
	ru=0;
	rd=0;
	bu=0;
	bd=0;
	//cout << red_p.size() << " " << blue_p.size() << "\n";
	for(ll i=0; i<red_p.size(); i++)
	{
		ll qt1 = (red_p[i].second - y1) * (x2-x1);
		ll qt2 = (red_p[i].first - x1)  * (y2-y1);
		if(qt1 > qt2) ++ru;
		else if(qt1 < qt2) ++rd;
	}
	
	
	
	for(ll i=0; i<blue_p.size(); i++)
	{
		ll qt1 = (blue_p[i].second - y1) * (x2-x1);
		ll qt2 = (blue_p[i].first - x1)  * (y2-y1);
		if(qt1 > qt2) ++bu;
		else if(qt1 < qt2) ++bd;
	}
	//cout << rd << " "  << ru << " " << bd << " " << bu << "\n";
	ll res = min(ru+bd,rd+bu);
	ans = min(ans, res);
}
int main()
{
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);
	//freopen("input.txt","r",stdin);
	//freopen("output.txt","w",stdout);
	ll t,n,m,x,y;
	pair<ll,ll>temp1;
	vector< pair<ll,ll> >red_points;
	vector< pair<ll,ll> >blue_points;
	cin >> t;
	while(t--)
	{
		cin >> n >> m;
		ans = n+m;
		pair<ll,ll>temp1;
		vector< pair<ll,ll> >red_points;
		vector< pair<ll,ll> >blue_points;
		for(ll i=0; i<n; i++)
		{
			cin >> x >> y;
			temp1 = make_pair(x,y);
			red_points.push_back(temp1);
		}
		
		for(ll i=0; i<m; i++)
		{
			cin >> x >> y;
			temp1 = make_pair(x,y);
			blue_points.push_back(temp1);	
		}
		
		/*
		for(ll i=0; i<red_points.size(); i++)
		{
			cout << red_points[i].first << " " << red_points[i].second << "\n";	
		}
		
		for(ll i=0; i<blue_points.size(); i++)
		{
			cout << blue_points[i].first << " " << blue_points[i].second << "\n";	
		}
		*/
		
		for(ll i=0; i<red_points.size()-1; i++)
		{
			if(red_points.size()<101 && blue_points.size()<101)
			{
				for(ll j=i+1; j<red_points.size(); j++)
				{
					calculate_line(red_points[i].first,red_points[i].second,red_points[j].first,red_points[j].second,red_points,blue_points);
				}
			}
			else
			{
				for(ll k=1; k<=limit; k++)
				{
					//ll j=i;
					ll j = rand() % red_points.size(); //hopefully generating random numbers
					if(j==i)
					    j = rand() % red_points.size();
					//cout << j << "\n";
					//for(ll j=i+1; j<red_points.size(); j++)
					{
						calculate_line(red_points[i].first,red_points[i].second,red_points[j].first,red_points[j].second,red_points,blue_points);
					}
				}
			}
			
		}
		for(ll i=0; i<blue_points.size()-1; i++)
		{
			if(red_points.size() <101 && blue_points.size() <101)
			{	
				for(ll j=i+1; j<blue_points.size(); j++)
				{
					calculate_line(blue_points[i].first,blue_points[i].second,blue_points[j].first,blue_points[j].second,red_points,blue_points);
				}		
			}			
			else
			{
				for(ll k=1; k<=limit; k++)
				{
					ll j = rand()% blue_points.size(); //hopefully generating random numbers
					if(j==i)
					    j = rand()% blue_points.size();
					//cout << j << "\n";
					//for(ll j=i+1; j<blue_points.size(); j++)
					{
						calculate_line(blue_points[i].first,blue_points[i].second,blue_points[j].first,blue_points[j].second,red_points,blue_points);
					}
				}
			}
			
		}
		if(n==1 && m==1)
			cout << 0 << "\n";
		else
			cout << ans << "\n";
				
	}
	return 0;
} 

```


