```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int N = 32;
		
		System.out.println(sol.solution(N));
	}
	public int solution(int N) {
		int answer = 0;
		
		String bin = Integer.toString(N, 2);
		
		int startPoint = 0;
		for(int i=1; i<bin.length(); i++) {
			if(bin.substring(i, i+1).equals("1")) {
				answer = Math.max(answer, i-startPoint-1);
				startPoint = i;
			}
		}
		
		return answer;
    }
}
```