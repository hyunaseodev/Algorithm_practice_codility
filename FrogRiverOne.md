```java
import java.util.HashMap;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int X = 5;
		int[] A = {1, 3, 1, 4, 2, 3, 5, 4};

		System.out.println(sol.solution(X, A));
	}
	public int solution(int X, int[] A) {
		HashMap<Integer, Integer> hm = new HashMap<>();
		
		for(int i=0; i<A.length; i++) {
			if(hm.get(A[i]) != null) {
				hm.put(A[i], Math.min(hm.get(A[i]), i));
			} else {
				hm.put(A[i], i);
			}
		}
		
		int answer = -1;
		
		if(hm.size() == X) {
			for(int i=1; i<=X; i++) {
				answer = Math.max(answer, hm.get(i));
			}
		}
		
		return answer;
    }
}
```