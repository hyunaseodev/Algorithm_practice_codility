```java
import java.util.HashSet;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();

		int[] A = {-5, -3, -1, 0, 3, 6};
		
		System.out.println(sol.solution(A));
	}
	
	public int solution(int[] A) {
		int answer = 0;
		
		HashSet<Integer> hs = new HashSet<>();
		
		for(int i : A) {
			if(i<0)
				hs.add((-1)*i);
			else
				hs.add(i);
		}
		
		answer = hs.size();
		
		return answer;
    }
}
```