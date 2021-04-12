# 832. Flipping an Image
```
class Solution {
    public int[][] flipAndInvertImage(int[][] image) {
        for(int i = 0; i < image.length; i++) {
        	int k = image[i].length - 1;
        	for(int j = 0; j <= k; j++) {
        		if(image[i][j] == image[i][k]) {
        			image[i][j] = (image[i][j] == 0) ? 1 : 0;
        			image[i][k] = image[i][j];
        		}
        		k--;
        	}
        }
		
		return image;
    }
}
```
### Time complexity: O(n*m)
#### Where n is length of image
#### Where m is length of image[]
### Space complexity: O(1)