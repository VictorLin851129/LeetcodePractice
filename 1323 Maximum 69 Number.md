# 1323. Maximum 69 Number
## First solution
```
class Solution {
    public int maximum69Number (int num) {
        String numStr = String.valueOf(num);
        int digit_front = numStr.indexOf("6");
        if (digit_front != -1) {
            int digit_rear = numStr.length() - digit_front - 1;
            int compute = digit_rear == 0 ? 3 : 3 * (int)Math.pow(10, digit_rear);
            num += compute;
        }

        return num;
    }
}
```
### Time complexity: O(n)
#### Where n is digit of num
### Space complexity: O(n)
#### Where n is digit of num
---
## Second solution
```
class Solution {
    public int maximum69Number (int num) {
        return Integer.parseInt(Integer.toString(num).replaceFirst("6", "9"));
    }
}
```
### Time complexity: O(n)
#### Where n is digit of num
### Space complexity: O(n)
#### Where n is digit of num
---
## Third solution
```
class Solution {
    public int maximum69Number (int num) {
        for(int i = (int) (Math.log10(num)); i >= 0; i--) {
			if((int)((num / Math.pow(10, i)) % 10) == 6) {
				num += 3 * Math.pow(10, i);
				break;
			}
		}
		
		return num;
    }
}
```
### Time complexity: O(n)
#### Where n is digit of num
### Space complexity: O(1)