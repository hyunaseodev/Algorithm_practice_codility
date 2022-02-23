```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {3, 8, 9, 7, 6};

		int K = 3;
		
		System.out.println(sol.solution(A, K));
	}
	public int[] solution(int[] A, int K) {
		int[] answer = new int[A.length];
		
		int A_len = A.length;
		
		if(A_len == 0) return answer;
		
		int cnt = K % A_len;
		
		for(int i=0; i<A_len; i++) {
			if(A_len-cnt+i < A_len) answer[i] = A[A_len-cnt+i];
			else answer[i] = A[i-cnt];
		}
		
		return answer;
		/*
		 * 참고
		int[] arr = new int[A.length];
		
		for(int i=0; i<A.length; i++) 
			arr[(i+K) % A.length] = A[i];
		
		return arr;
		 */
    }
}
```