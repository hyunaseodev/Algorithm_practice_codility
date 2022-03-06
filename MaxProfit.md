```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();

		int[] A = {23171, 21011, 21123, 21366, 21013, 21367};
		
		System.out.println(sol.solution(A));
	}
	
	public int solution(int[] A) {
		int answer = 0;

		int min = 0;
		if(A.length != 0)
			min = A[0];
		
		for(int i=0; i<A.length; i++) {
			min = Math.min(min, A[i]);
			answer = Math.max(answer, A[i]-min);
		}
		answer = answer > 0? answer : 0;
		
		return answer;
    }
}
```