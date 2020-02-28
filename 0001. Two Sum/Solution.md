## Intuition

 - Best-Concivable-Complexity: 
	 - Time: O(n).
	 - Space: O(n).
 - In order to return indices of pairs, we need to record the indices with corresponding numbers. Therefore, we can use a map with key as numbers and value as indices.

## Solution
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; i++){
            int remain = target - nums[i];
            if (map.containsKey(remain)){
                return new int[] {i, map.get(remain)};
            }
            map.put(nums[i],i);
        }
        throw new IllegalArgumentException("No result!");
    }
    
}
```