# *617. Merge Two Binary Trees
## Recursive solution
```
class Solution {
    public TreeNode mergeTrees(TreeNode root1, TreeNode root2) {
       if(root1 == null) {
			return root2;
		}
		if(root2 == null) {
			return root1;
		}
        root1.val += root2.val;
        ans.left = mergeTrees(root1.left, root2.left);
        ans.right = mergeTrees(root1.right, root2.right);
        return root1;
    }
}
```
### Time complexity: O(n)
#### Where n is min nodes of root1 and root2
### Space complexity: O(1)
---
## Iterative solution
```
class Solution {
    public TreeNode mergeTrees(TreeNode root1, TreeNode root2) {
       if(root1 == null) {
			return root2;
		}
		
		if(root2 == null) {
			return root1;
		}
		
		Queue<TreeNode> queue = new LinkedList<TreeNode>();
		queue.add(root1);
		queue.add(root2);
		
		while(!queue.isEmpty()) {
			TreeNode temp1 = queue.remove();
			TreeNode temp2 = queue.remove();
			if(temp1 != null && temp2 != null) {
				temp1.val += temp2.val;
				if(temp1.left == null) {
					temp1.left = temp2.left;
				}else {
					queue.add(temp1.left);
					queue.add(temp2.left);
				}
				if(temp1.right == null) {
					temp1.right = temp2.right;
				}else {
					queue.add(temp1.right);
					queue.add(temp2.right);
				}
			}
			
			
		}
		
		return root1;
    }
}
```
### Time complexity: O(n)
#### Where n is min nodes of root1 and root2
### Space complexity: O(m)
#### Where m max nodes of one layer