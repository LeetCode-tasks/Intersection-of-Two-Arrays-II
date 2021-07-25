# Intersection of Two Arrays II

Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.

### Example:

**_Input:_** `nums1 = [1,2,2,1], nums2 = [2,2]`

**_Output:_** `[2,2]`

### Constraints:

`1 <= nums1.length, nums2.length <= 1000`

`0 <= nums1[i], nums2[i] <= 1000`


## Solution in JavaScript:

```
var intersect = function(nums1, nums2) {
    let mapNums1 = {};
    let intersectionOfArrays = [];
    
    for (let i = 0; i < nums1.length; i++) {
        nums1[i] in mapNums1 ? mapNums1[nums1[i]]++ : mapNums1[nums1[i]] = 1;
    }
    
    for (let j = 0; j < nums2.length; j++) {
        if (nums2[j] in mapNums1 && mapNums1[nums2[j]] > 0) {
            intersectionOfArrays.push(nums2[j]);
            mapNums1[nums2[j]]--;
        }
    }
    
    return intersectionOfArrays;
};
```
