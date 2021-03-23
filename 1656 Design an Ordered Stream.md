# 1656. Design an Ordered Stream
## Set the pointer and wait until the loc of pointer exist string, then use iterator to add in map or list
## First solution
```
class OrderedStream {
    int pointer = 1;
	Map <Integer, String> m = new HashMap<Integer, String>();
    public OrderedStream(int n) {
    }
    
    public List<String> insert(int idKey, String value) {
        List<String> ans = new LinkedList<String>();
			m.put(idKey, value);
			
			if(m.containsKey(pointer)) {
				while(m.containsKey(pointer)) {
					ans.add(m.remove(pointer++));
				}
			}
			return ans;
    }
}
```

### Time complexity: O(n)
#### Where n is length of insert elements
### Space complexity: O(n)
#### Where n is length of insert elements
---
## Second solution
```
class OrderedStream {
		int pointer = 1;
		String[] StringSet;
		
	    public OrderedStream(int n) {
	    	pointer = 1;
	    	StringSet = new String[n + 1];
	    }
	    
		public List<String> insert(int idKey, String value) {
	    	List<String> ans = new LinkedList<String>();
			StringSet[idKey] = value;
			
			if(idKey == pointer) {
				while(pointer < StringSet.length && StringSet[pointer] != null) {
					ans.add(StringSet[pointer++]);
				}
			}
			return ans;
	    }
	}
```
### Time complexity: O(n)
#### Where n is length of insert elements
### Space complexity: O(n)
#### Where n is length of insert elements