# SNWTD

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

### Target Digit Sum

You are given a sorted array $A$ of $N$ positive integers and an integer $D$.

The  **digit sum**  of an integer is the sum of all its decimal digits. For example, the digit sum of $123$ is $1+2+3=6$.

Find the  **smallest integer**  in the array whose digit sum is exactly $D$.

If no such integer exists, print $-1$.

### Input Format
- The first line contains an integer $N$ — the number of elements in the array.
- The second line contains $N$ space-separated integers $A_1,A_2,\ldots,A_N$ in increasing order.
- The third line contains an integer $D$ — the required digit sum.
### Output Format
- Print the smallest integer in the array whose digit sum is equal to $D$.
- If no such integer exists, print $-1$.
### Constraints
- $1 \le N \le 20$
- $10 \le A_i \le 1000$
- $A_1 \lt A_2 \lt \cdots \lt A_N$
- $1 \le D \le 27$
### Sample 1:
Input
Output

```
5
12 23 30 48 56
3
```

```
12
```

### Explanation:

The digit sum of $12$ is $1+2=3$.

Since $12$ is the smallest number in the array with digit sum $3$, the answer is $12$.

### Sample 2:
Input
Output

```
5
23 45 67 68 95
17
```

```
-1
```

### Explanation:

No number in the array has a digit sum equal to $17$, so the answer is $-1$.

## Solution

**Language:** c_cpp  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-11-04T16:43:06.670Z  

```c_cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n;
	cin>>n;
	vector<int> v;
	for(int i =0;i<n;i++){
	    int a ;
	    cin>>a;
	    v.push_back(a);
	}
	int d;
	cin>>d;
	sort(v.begin(),v.end());
	int number=-1;
	for(int i=0;i<v.size();i++){
	    int num=v[i],sum=0;
	    while(num>0){
	        int reminder=num%10;
	        sum+=reminder;
	        num/=10;
	    }
	    if(sum==d){
	        number=v[i];
	        break;
	    }
	}
	cout<<number<<endl;

}

```

---

[View on CodeChef](https://www.codechef.com/problems/SNWTD)