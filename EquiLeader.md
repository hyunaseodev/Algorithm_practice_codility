```java
import java.util.*;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();

		int[] A = {4, 3, 4, 4, 4, 2};
		
		System.out.println(sol.solution(A));
	}
	
	private int dominator;
	private int dominatorCount;
	
	public int solution(int[] A) {
		Map<Integer, Integer> counters = new HashMap<>();
		for(int i=0; i<A.length; i++) {
			int a = A[i];
			counters.put(a, counters.getOrDefault(a, 0)+1);
			
			if(counters.get(a) > A.length/2) {
				dominator = a;
				dominatorCount = counters.get(a);
			}
		}
		
		int equiLeaders = 0;
		
		int leadersInRightSide = dominatorCount;		
		int countRightSide = A.length;
		int countLeftSide = 0;
		int leadersInLeftSide = 0;
		for(int i=0; i<A.length; i++) {
			if(A[i] == dominator) {
				leadersInRightSide--;
				leadersInLeftSide++;
			}
			countLeftSide++;
			countRightSide--;
			
			if(leadersInLeftSide > countLeftSide / 2) {
				if(leadersInRightSide > countRightSide / 2) {
					equiLeaders++;
				}
			}
		}
		
		return equiLeaders;
    }
}
```