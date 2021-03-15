# 1773. Count Items Matching a Rule
## Check type first, then find out matching value
## First solution
```
class Solution {
    public int countMatches(List<List<String>> items, String ruleKey, String ruleValue) {
        int result = 0;
		int type = 0;
		
		if(ruleKey.equals("type")) {
			type = 0;
		}else if(ruleKey.equals("color")) {
			type = 1;
		}else{	//name
			type = 2;
		}
		
		for(int i = 0; i < items.size(); i++)
			if(items.get(i).get(type).equals(ruleValue)) {
				result++;
			}
		
        return result;
    }
}
```

### Time complexity: O(n)
#### Where n is length of items
### Space complexity: O(1)
---
## Second solution
```
class Solution {
    public int countMatches(List<List<String>> items, String ruleKey, String ruleValue) {
        int result = 0;
		int type = ruleKey.equals("type") ? 0 : ruleKey.equals("color") ? 1 : 2;
		
		for(List<String> i : items) {
			if(i.get(type).contentEquals(ruleValue))
				result++;
		}
		
        return result;
    }
}
```
### Time complexity: O(n)
#### Where n is length of items
### Space complexity: O(1)




