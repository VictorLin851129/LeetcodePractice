# 1732. Find the Highest Altitude
```
class Solution {
    public int largestAltitude(int[] gain) {
        int maxAltitude = Math.max(0, gain[0]);
        
        for(int i = 1; i < gain.length; i++) {
        	gain[i] = gain[i] + gain[i - 1];
        	if(gain[i] > maxAltitude) {
        		maxAltitude = gain[i];
        	}
        }
        	
		return maxAltitude;
    }
}
```
### Time complexity: O(n)
#### Where n is length of gain
### Space complexity: O(1)