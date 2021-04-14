# 1436. Destination City
```
class Solution {
    public String destCity(List<List<String>> paths) {
        List<String> list = new ArrayList<String>();
		
		for(int i = 0; i < paths.size(); i++) {
			list.add(paths.get(i).get(0));
		}
		for(int i = 0; i < paths.size(); i++) {
			if(!list.remove(paths.get(i).get(1))) {
				return paths.get(i).get(1);
			}
		}
			
		return null;
    }
}
```
### Time complexity: O(n)
#### Where n is length of paths
### Space complexity: O(n)
#### Where n is length of paths