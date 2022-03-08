```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {0, 1, 0, 1, 1};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		long answer = 0;
		
		long sum = 0;
		for(int i:A)
			sum += (long)i;
	
		long pre_sum = 0;
		for(int i=0; i<A.length-1; i++) {
			pre_sum += A[i];
			
			if(A[i] == 0)
				answer += sum - pre_sum;
		}
		
		if(answer > 1000000000) 
			answer = -1;
		
		return (int)answer;
    }
}
```