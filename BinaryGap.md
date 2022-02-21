```java
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int N = 32;
		
		System.out.println(sol.solution(N));
	}
	public int solution(int N) {
		int answer = 0;
		
		String str = Integer.toBinaryString(N);
		char[] chr = str.toCharArray();
		
		int tmp = 0;
		for(char c : chr) {
			//0이면 tmp++;
			//1이면 answer와 tmp중 큰 값을 answer에 대입하고 tmp는 0으로 치환
			if(c == '0') {
				tmp++;
			} else {
				answer = Math.max(answer, tmp);
				tmp = 0;
			}
		}
		
		return answer;
    }
}
```