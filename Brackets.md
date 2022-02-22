```java
import java.util.Stack;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		String s = "{[()()]}";
		//{10, 50, 5, 1};

		System.out.println(sol.solution(s));
	}
	
	public int solution(String s) {
		int answer = 0;
		
		char[] chr = s.toCharArray();
		
		Stack<Character> stk = new Stack<>();
		
		for(int i=0; i<chr.length; i++) {
			char c = chr[i];
			if(stk.isEmpty()) {
				stk.add(c);
			} else {
				if(c == ')' && stk.peek() == '(') {
					stk.pop();
				} else if(c == '}' && stk.peek() == '{') {
					stk.pop();
				} else if(c == ']' && stk.peek() == '[') {
					stk.pop();
				} else {
					stk.add(chr[i]);
				}
			}
		}
		
		if(stk.size() == 0) answer = 1;
		else answer = 0;
		
		return answer;
    }
}
```