```

# Monsijb
 
# Reference : http://www.geeksforgeeks.org/python-input-methods-competitive-programming/
import atexit, io, sys
 
buffer = io.BytesIO()
sys.stdout = buffer
 
 
@atexit.register
def write():
    sys.__stdout__.write(buffer.getvalue())
    
n, m = map(int, raw_input().split())
mylist=list(map(int,raw_input().split()))
while m > 0:
	t, x, y= map(int, raw_input().split())
	x -=1
	if t == 1:
		mylist[x] = y
	else :
		ans = 0
		cnt = 0
		for i in xrange(x+1):
			ans = ans ^ mylist[i]
			if ans == y:
				cnt +=1
		print(cnt)
	m-=1 
	
	
```

