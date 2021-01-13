# 771. Jewels and Stones
## Check if the characters in jewels are match with characters in stones.
## First solution
```
class Solution {
    public static int numJewelsInStones(String jewels, String stones) {
		int diamond = 0;
        
        for(int i = 0; i < stones.length(); i++) {
			if(jewels.indexOf(stones.charAt(i)) != -1) {
				diamond++;
			}
		}
		
//Other method
//		for(int i = 0; i < jewels.length(); i++) {
//			for(int j = 0; j < stones.length(); j++) {
//				if(jewels.charAt(i) == stones.charAt(j)) {
//					diamond++;
//				}
//			}
//		}
        
        return diamond;
    }
}
```

### Time complexity: O(m*n)
#### m is length of jewels 
#### n is length of stones
### Space complexity: O(1)
---
## Second solution

```
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int diamond = 0;
		
		HashMap<Character, Integer> check = new HashMap<Character, Integer>();
		
		for(int i = 0; i < stones.length(); i++) {
			if(check.get(stones.charAt(i)) == null) {
				check.put(stones.charAt(i), 1);
			}else {
				int precount = check.get(stones.charAt(i));
				check.put(stones.charAt(i), ++precount);
			}
		}
		
		for(int i = 0; i < jewels.length(); i++) {
			if(check.get(jewels.charAt(i)) != null) {
				diamond+=check.get(jewels.charAt(i));
			}
		}
        

//Other method
//		Set check = new HashSet<>();
//		
//		for(char j: jewels.toCharArray()) {
//			check.add(j);
//		}
//		
//		for(char s: stones.toCharArray()) {
//			if(check.contains(s)) {
//				diamond++;
//			}
//		}
//		
        
        return diamond;
    }
}
```
### Time complexity: O(m+n)
#### m is length of jewels 
#### n is length of stones
### Space complexity: O(1)




