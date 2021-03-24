# 1290. Convert Binary Number in a Linked List to Integer
## Add each node's value then multiply 2 by operator <<
```
class Solution {
    public int getDecimalValue(ListNode head) {
        int ans = 0;
		while(head.next != null) {
			ans += head.val;
			ans <<= 1;
			head = head.next;
		}

        return ans + head.val;
    }
}
```
### Time complexity: O(n)
#### Where n is length of ListNode
### Space complexity: O(1)