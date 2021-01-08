# 1108. Defanging an IP Address
## Move each element to the correct place
## First solution

```
class Solution {
    public String defangIPaddr(String address) {
        return address.replace(".", "[.]");
    }
}
```

### Time complexity: O(1)
#### Because the range of IPv4 address is from 0.0.0.0 to 255.255.255.255
### Space complexity: O(1)
---
## Second solution

```
class Solution {
    public String defangIPaddr(String address) {
        String results = "";
		for(int i = 0; i < address.length(); i++) {
			results += (address.charAt(i) == '.') ? "[.]" : address.charAt(i);
		}
		return results;
    }
}
```

### Time complexity: O(1)
### Space complexity: O(1)