# 1281. Subtract the Product and Sum of Digits of an Integer
## Use while loop to check if num still have digit to calculate
### Time complexity: O(log(n))
#### n is input number
#### O(log(n)) since we are dividing by 10  (Just like Binary Search on how we divide the options).
### Space complexity: O(1)
```
class Solution {
    public int subtractProductAndSum(int n) {
        int sum = 0, product = 1;
		
		while(n > 0) {
			sum += (n % 10);
			product *= (n % 10);
			n /= 10;
		}

		return product - sum;
    }
}
```