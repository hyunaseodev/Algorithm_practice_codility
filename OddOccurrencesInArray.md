```java
import java.util.HashMap;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {9,3,9,3,9,7,9};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		int answer = -1;
		HashMap<Integer, Integer> hm = new HashMap<Integer, Integer>();
		
		
		for(int i : A) {
			hm.put(i, hm.getOrDefault(i, 0)+1);
		}
		
		for(int i : hm.keySet()) {
			//횟수가 홀수인 경우
			if(hm.get(i) % 2 == 1) answer = i; 
		}
		
		return answer;		
    }
}
```