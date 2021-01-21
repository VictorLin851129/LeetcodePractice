# 1512. Number of Good Pairs
## For each i, finds all j where, j < i && nums[j] == nums[i];
## First solution
```
public static int numIdenticalPairs(int[] nums) {
    HashMap<Integer, Integer> count = new HashMap<Integer, Integer>();
    int ans = 0;

    for(int i = 0; i < nums.length; i++) {
        if(!count.containsKey(nums[i])) {
            count.put(nums[i], 1);
        }else {
            ans += count.get(nums[i]);
            count.put(nums[i], count.get(nums[i]) + 1);
        }
    }

    for (HashMap.Entry<Integer, Integer> m : count.entrySet()) {
        ans += choose(m.getValue(), 2);
    }

    return ans;
}
	
public static long choose(long total, long choose){
    if(total < choose)
        return 0;
    if(choose == 0 || choose == total)
        return 1;
    return choose(total-1,choose-1)+choose(total-1,choose);
}
```

### Time complexity: O(2n + 2^n) = O(2^n)
#### n is length of array
### Space complexity: O(n)
---
## Second solution

```
public static int numIdenticalPairs(int[] nums) {
    Map<Integer, Integer> map = new HashMap<>();
    int count = 0;
    for (int num : nums) {
      count += map.getOrDefault(num, 0);
      map.put(num, map.getOrDefault(num, 0) + 1);
    }

    return count;
}
```
### Time complexity: O(n)
#### n is length of array
### Space complexity: O(n)




