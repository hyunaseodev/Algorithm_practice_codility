```java
import java.util.Stack;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {4, 3, 2, 1, 5};
		int[] B = {1, 1, 0, 0, 0};
		
		System.out.println(sol.solution(A, B));
	}
	
	public int solution(int[] A, int[] B) {
		if(A.length == 0)
			return 0;
		
		Stack<Integer> stk = new Stack<>();
		int numAlive = A.length;
		
		for(int i=0; i<A.length; i++) {
			if(B[i] == 1) {
				stk.push(A[i]);
			}
			
			if(B[i] == 0) {
				while(!stk.isEmpty()) {
					if(stk.peek() > A[i]) {
						numAlive--;
						break;
					}
					else if(stk.peek() < A[i]) {
						numAlive--;
						stk.pop();
					}
				}
			}
			
		}
		
		return numAlive;
    }
}
```