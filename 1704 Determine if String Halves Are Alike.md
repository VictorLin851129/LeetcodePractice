# 1704. Determine if String Halves Are Alike
## First solution
```
class Solution {
    public int result(String s, int l, int r, boolean[] arr, int count) {
        while(l < r){
            if(arr[s.charAt(l)-65]) count++;
            l++;
        }
        return count;
    }
    public boolean halvesAreAlike(String s) {
        boolean arr[] = new boolean[122-65+1]; 
        arr['a'- 65] = arr['e'- 65] = arr['i'- 65] = arr['o'- 65] = arr['u'- 65] = arr['A'-65] = arr['E'-65] = arr['I'- 65] = arr['O'-65] = arr['U'-65] = true; 
        return result(s, 0, s.length() / 2, arr, 0) == result(s, s.length() / 2, s.length(), arr, 0);
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(1)
---
## Second solution
```
class Solution {
    public boolean halvesAreAlike(String s) {
        int vowels = 0;
		int length = s.length();
		for(int i = 0; i < length / 2; i++) {
			if("aeiouAEIOU".contains(Character.toString(s.charAt(i)))) {
				vowels++;
			}
		}
		
		for(int i = length / 2; i < length; i++) {
			if("aeiouAEIOU".contains(Character.toString(s.charAt(i)))) {
				vowels--;
			}
		}
		
		System.out.println(vowels);
		return vowels == 0;
    }
} 
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(1)