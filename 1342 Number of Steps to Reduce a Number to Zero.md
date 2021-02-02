# 1342. Number of Steps to Reduce a Number to Zero
## Use while loop to check if num is even or not
### Time complexity: O(log(n))
#### n is input number
#### O(log(n)) since we are dividing by 2 when even (Just like Binary Search on how we divide the options).
### Space complexity: O(1)
```
class Solution {
    public int numberOfSteps (int num) {
        int count = 0;
		
		while(num > 0) {
			if(num % 2 == 1) {
				num-=1;
			}else {
				num /= 2;
			}
			count++;
		}
		
		return count;
    }
}
```