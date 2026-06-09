## Problems

### 1. Two Sum

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

> [!example]
**Example 1:**
>
**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

> [!example]
**Example 2:**
>
**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]

> [!example]
**Example 3:**
>
**Input:** nums = [3,3], target = 6
**Output:** [0,1]

**Constraints:**
- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

```cpp
class Solution {
	public:
		vector<int> twoSum(vector<int>& nums, int target) {
			unordered_map<int, size_t> u;
			
			for (size_t i = 0; i < nums.size(); ++i) {
				u.insert({nums[i], i});
			}
			
			for (size_t i = 0; i < nums.size(); ++ i) {
				int key = target - nums[i];
				
				if (size_t val = u.find(key); val != nums.end()) {
					return {i, val};
				}
			}
			
			return {};
		}
};
```