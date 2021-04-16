# 905. Sort Array By Parity
```
class Solution {
    public int[] sortArrayByParity(int[] A) {
        int front = 0, rear = A.length - 1;
		while(front < rear) {
			while(A[front] % 2 == 0 && front < A.length - 1) {
				front++;
			}
			while(A[rear] % 2 != 0 && rear > 0) {
				rear--;
			}
			if(front < rear) {
				int temp = A[front];
				A[front] = A[rear];
				A[rear] = temp;
			}
			front++;
			rear--;
		}
		
		return A;
    }
}
```
### Time complexity: O(n)
#### Where n is length of A
### Space complexity: O(1)