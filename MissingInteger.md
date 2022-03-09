```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {-1, -3};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		boolean[] dp = new boolean[1000001];
		
		for(int i:A) {
			if(i > 0)
				dp[i] = true;
		}
		
		for(int i=1; i<=1000000; i++) {
			if(dp[i] == false)
				return i;
		}
		
		return -1;
		
		/*
		 * 실패(시간초과)
		int answer = 0;
		
		TreeSet<Integer> ts = new TreeSet<>();
		
		for(int i:A) {
			ts.add(i);
		}
		
		for(int i=1; i<=1000000; i++) {
			if(!ts.contains(i)) {
				return i;
			}
		}
		
		return answer;
		 */
    }
}
```