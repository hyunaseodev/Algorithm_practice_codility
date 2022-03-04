```java
import java.util.Arrays;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {4, 1, 3};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		int answer = 1;
		
		Arrays.sort(A);
		
		int check = 1;
		for(int i=0; i<A.length; i++) {
			if(A[i] != check) {
				return answer=0;
			} else {
				check++;
			}
		}
		
		return answer;
    }
}
```