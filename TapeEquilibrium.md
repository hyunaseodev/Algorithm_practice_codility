```java
import java.util.Arrays;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {3, 1, 2, 4, 3};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		int answer = 0;
		
		int A_len = A.length;
		
		long[] tmp = new long[A_len];
		for(int i=0; i<A_len; i++) {
			if(i == 0) {
				tmp[i] = A[i]; 
			} else {
				tmp[i] = tmp[i-1] + A[i]; 
			}
		}
		
		long[] tmp2 = new long[A_len-1];
		for(int i=0; i<tmp2.length; i++) {
			tmp2[i] = Math.abs(tmp[A_len-1] - 2*tmp[i]);
		}
		
		Arrays.sort(tmp2);
		answer = (int)tmp2[0];
		
		return answer;
    }
}
```