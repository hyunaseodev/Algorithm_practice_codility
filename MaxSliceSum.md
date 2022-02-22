```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();

		int[] A = {-3, -2, -6, 4, 8};
		
		System.out.println(sol.solution(A));
	}
	
	public int solution(int[] A) {
		long sum = Integer.MIN_VALUE;
		long maxSum = Integer.MIN_VALUE;
		
		for(int a : A) {
			sum = Math.max(sum + a, a);
			maxSum = Math.max(sum, maxSum);
		}
		
		return (int)maxSum;
    }
}
```