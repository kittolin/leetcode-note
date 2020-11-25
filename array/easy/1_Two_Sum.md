## [题目](https://leetcode.com/problems/two-sum/)
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

Example 1:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
```

Example 2:
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

Example 3:
```
Input: nums = [3,3], target = 6
Output: [0,1]
```

## [自己的解法](https://leetcode.com/submissions/detail/422939254/)
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; i++) {
            if(map.containsKey(target - nums[i])) {
                return new int[]{map.get(target - nums[i]), i};
            }
            map.put(nums[i], i);
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}
```

Result:
- Runtime: 0 ms, 100.00 %
- Memory Usage: 39.1 MB, 52.65 %
- Time complexity: O(n)
- Space complexity: O(n)

## 总结思考
- 利用 map，空间换时间
- 遍历数组，将数字和对应的索引存入 map 中
- 遍历过程中同时判断数字的补数在集合中是否存在
