
[[Topics/2 Way Merge Sort]]
[[Topics/Strassen’s Matrix Multiplication]]

### Introduction
The divide and conquer approach, works by dividing a given problems into smaller subproblems which then intergrade back to the final solution.

```pseudo
General algorithm

D&C(P)
	if small(P) then return S(P);
	else{
		divide into smaller instances, P1, P2 ..
		Apply D&C to each subproblem
		combine all subproblems
	}

```

