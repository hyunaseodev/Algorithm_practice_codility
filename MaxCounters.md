```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int N = 5;
		int[] A = {3, 4, 4, 6, 1, 4, 4};

		System.out.println(sol.solution(N, A));
	}
	public int[] solution(int N, int[] A) {
		int[] answer = new int[N];
		
		int nowMax = 0;
		int preMax = 0;
		
		for(int i=0; i<A.length; i++) {
			if(A[i] > N) {
				preMax = nowMax;
				System.out.println(preMax);
			} else {
				if(answer[A[i]-1] > preMax)
					answer[A[i]-1]++;
				else
					answer[A[i]-1] = preMax + 1;
				
				if(answer[A[i]-1] > nowMax)
					nowMax = answer[A[i]-1];
			}
		}
		
		for(int i=0; i<answer.length; i++) {
			if(answer[i] < preMax)
				answer[i] = preMax;
		}
		
		return answer;
/*
 *실패(시간초과) 
		int[] answer = new int[N];
		
		int max = 0;
		for(int K=0; K<A.length; K++) {
			if(1<=A[K] && A[K]<=N) {
				answer[A[K]-1] += 1;
				max = (max > answer[A[K]-1])? max : answer[A[K]-1];//Math.max(max, answer[A[K]-1]);
			} else if(A[K] == N+1) {
				Arrays.fill(answer, max);
			}
		}
		
		return answer;
*/		
    }
}
```