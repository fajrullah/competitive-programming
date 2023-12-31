````
Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:
Input: nums = [3,3], target = 6
Output: [0,1]
````
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    // store index
    const indices = {};
    for(let i = 0; i < nums.length; i++){
        // get the difference
        const difference = target - nums[i];
        // if the difference on there the return the index of array
        if(difference in indices){
            return [indices[difference], i]
        }
        indices[nums[i]] = i
    }
    return []
};
