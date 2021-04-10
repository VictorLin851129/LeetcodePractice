# 804. Unique Morse Code Words
```
class Solution {
    public int uniqueMorseRepresentations(String[] words) {
        Set<String> codeSet = new HashSet<String>();
        String[] code = {".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."};
        
        for(String s : words) {
        	StringBuilder sb = new StringBuilder();
        	for(char c : s.toCharArray()){
        		sb.append(code[c - 'a']);
        	}
        	codeSet.add(sb.toString());
        }
        
        return codeSet.size();
    }
}
```
### Time complexity: O(n*m)
#### Where n is length of words
#### Where m is length of char in each word
### Space complexity: O(26 + n)
#### Where n is length of words