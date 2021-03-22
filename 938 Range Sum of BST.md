# (*)938. Range Sum of BST
## Check all node's value and compare with low and high value
## First solution
```
class Solution {
    public int rangeSumBST(TreeNode root, int low, int high) {
        int ans = 0;
		Stack<TreeNode> treeStack= new Stack<TreeNode>(); 
		treeStack.push(root);
		while(!treeStack.isEmpty()) {
			TreeNode top = treeStack.pop();
			
			if((top.val >= low) && (top.val <= high)) {
				ans += top.val;
			}
			
			if(top.right != null) {
				treeStack.push(top.right);
			}
			
			if(top.left != null) {
				treeStack.push(top.left);
			}
		}
		
		return ans;
    }
}
```

### Time complexity: O(n)
#### Where n is length of node
### Space complexity: O(n)
#### Where n is length of node
---
## Second solution
```
class Solution {
    public int rangeSumBST(TreeNode root, int low, int high) {
        return calAns(root, low, high, 0);
    }
    
    public int calAns(TreeNode node, int low, int high, int ans) {
		if(node == null) {
			return 0;
		}
		//System.out.println(node.val);
		
		if(node.left != null) {
			ans = calAns(node.left, low, high, ans);
		}
		if(node.right != null) {
			ans = calAns(node.right, low, high, ans);
		}
		
		if((node.val >= low) && (node.val <= high)) {
			//System.out.println(node.val);
			return ans += node.val;
		}
		return ans;
	}
}
```
### Time complexity: O(nlog(n))
#### Where n is count of nodes
### Space complexity: O(1)
---
## Third solution
```
class Solution {
    public int rangeSumBST(TreeNode root, int low, int high) {
        if(root == null) {
			return 0;
		}
		
		int val = root.val;
		
		if(val < low) {
			return rangeSumBST(root.right, low, high);
		}else if(val > high) {
			return rangeSumBST(root.left, low, high);
		}else {
			return val + rangeSumBST(root.left, low, high) + rangeSumBST(root.right, low, high);
		}
    }
    
    
}
```
### Time complexity: O(nlog(n))
#### Where n is count of nodes
### Space complexity: O(1)



