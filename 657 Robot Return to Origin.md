# 657. Robot Return to Origin
```
class Solution {
    public boolean judgeCircle(String moves) {
        int vertical = 0, horizontal = 0;
		
		for(char c : moves.toCharArray()) {
			if(c == 'R') {
				horizontal += 1;
			}else if(c == 'L') {
				horizontal -= 1;
			}else if(c == 'U') {
				vertical += 1;
			}else if(c == 'D'){
				vertical -=1;
			}
		}
		
		return vertical == 0 && horizontal == 0;
    }
}
```
### Time complexity: O(n)
#### Where n is length of moves
### Space complexity: O(1)