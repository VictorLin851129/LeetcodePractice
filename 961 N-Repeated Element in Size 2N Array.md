# 961. N-Repeated Element in Size 2N Array
```
class Solution {
    public int repeatedNTimes(int[] A) {
        Set<Integer> set = new HashSet<Integer>();
		for(int i : A) {
			if(set.contains(i)) {
				return i;
			}
			set.add(i);
		}
		throw null;
    }
}
```
### Time complexity: O(n)
#### Where n is length of A
### Space complexity: O(n)
#### Where n is length of A