# 1812. Determine Color of a Chessboard Square
#### Use ASCII code to get the sum and check if it is odd or even. even means it is true.
```
class Solution {
    public boolean squareIsWhite(String coordinates) {
        return (coordinates.charAt(0) - 97 + coordinates.charAt(1) - 48) % 2 == 0;
    }
}
```
### Time complexity: O(1)
### Space complexity: O(1)