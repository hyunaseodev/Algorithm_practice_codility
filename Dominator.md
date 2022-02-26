```java
import java.util.HashMap;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();

		int[] A = {0,0,1,1,1};
		
		System.out.println(sol.solution(A));
	}
	
	public int solution(int[] A) {
		HashMap<Integer, Integer> hm = new HashMap<>();
		
		for(int i : A) {
			hm.put(i, hm.getOrDefault(i, 0)+1);
		}
		
		int answer = -1;
		int std = (int) Math.floor((double)A.length/2);
		for(int i : hm.keySet()) {
			if(hm.get(i) > std) {
				for(int j=0; j<A.length; j++) {
					if(A[j] == i) return answer = j;
				}
			}
		}
		
		return answer;
    }
}
```