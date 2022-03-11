```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] A = {2, 3, 1, 5};

		System.out.println(sol.solution(A));
	}
	public int solution(int[] A) {
		int answer = 0;
		
		int[] tmp = new int[A.length+1];
		
		for(int i : A) {
			tmp[i-1] = 1;
		}
		
		for(int i=0; i<tmp.length; i++) {
			if(tmp[i] != 1) {
				answer = i+1; 
				break;
			}
		}
		
		return answer;
    }
}
```