# 1678. Goal Parser Interpretation
## Replace "()" with 'o' and replace "(al)" with "al"
## First solution

```
class Solution {
    public String interpret(String command) {
        StringBuilder sb = new StringBuilder(command.length());
        for (int i=0; i < command.length(); i++){
            if (command.charAt(i) == 'G'){
                sb.append("G");
            }
            if (command.charAt(i) == '('){
                if (command.charAt(i+1) == ')'){
                    sb.append("o");
                    i++;
                }
                else{
                    sb.append("al");
                    i = i+3;
                }
            }
        }
        
        return sb.toString();
    }
}
```

### Time complexity: O(n)
#### where n is the length of input
### Space complexity: O(n)
#### where n is the length of input
---
## Second solution

```
class Solution {
    public String interpret(String command) {
        return command.replace("()","o").replace("(al)","al");
    }
}```
```

### Time complexity: O(n)
#### where n is the length of input
### Space complexity: O(n)
#### where n is the length of input