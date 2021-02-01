# 1603. Design Parking System
## Check if parking lot greater than 0
## First solution
```
class ParkingSystem {
	int big = 0;
    int medium = 0;
    int small = 0;
    public ParkingSystem(int big, int medium, int small) {
        this.big = big;
        this.medium = medium;
        this.small = small;
    }
    
    public boolean addCar(int carType) {
    	if(carType == 1) {
    		big -= 1;
    		return big < 0 ? false : true;
    	}else if(carType == 2) {
    		medium -=1 ;
    		return medium < 0 ? false : true;
    	}else if(carType == 3){
    		small -= 1;
    		return small < 0 ? false : true;
    	}else {
    		return false;
    	}
    	
    }
}
```

### Time complexity: O(1000) = O(1)
#### Cause addCar will not greater than 1000 times
### Space complexity: O(3) = O(1)
---
## Second solution
```
class ParkingSystem {
    private int[] sizes;
    public ParkingSystem(int big, int medium, int small) {
        this.sizes = new int[]{big,medium,small};
    }
    
    public boolean addCar(int carType) {
        return this.sizes[carType -1] --> 0;
    }
}
```
## i -\-> 0 means i > 0; i-\-;

### Time complexity: O(1000) = O(1)
#### Cause addCar will not greater than 1000 times
### Space complexity: O(3) = O(1)




