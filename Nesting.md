```java
import java.util.Stack;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		String S = "(()(())())";
		
		System.out.println(sol.solution(S));
	}
	
	public int solution(String S) {
		char[] chr = S.toCharArray(); 
		
		Stack<Character> stk = new Stack<>();
		
		for(char c : chr) {
			if(c == '(') {
				stk.add(c);
			} else {
				if(!stk.isEmpty() && stk.peek() == '(') {
					stk.pop();
				} else {
					stk.add(c);
				}
			}
		}
		
		int answer = stk.size() == 0? 0 : 1;
		return answer;
    }
}
```