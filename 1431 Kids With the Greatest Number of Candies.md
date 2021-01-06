# 1431. Kids With the Greatest Number of Candies
## Find the maximize value in array first. Then, add extraCandies with each value in the array and compare it with maximize value we get before.
### Time complexity: O(n)
### Space complexity: O(n)
```
class Solution {
    public List<Boolean> kidsWithCandies(int[] candies, int extraCandies) {
        int maxVal = 0;
		List<Boolean> results = new ArrayList();
		for(int i = 0; i < candies.length; i++) {
			if(candies[i] > maxVal) {
				maxVal = candies[i];
			}
		}
		for(int i = 0; i < candies.length; i++) {
			if(candies[i] + extraCandies >= maxVal) {
				results.add(true);
			}else {
				results.add(false);
			}
		}
		return results;
    }
}
```