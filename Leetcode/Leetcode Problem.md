
## [45. Jump Game II](https://leetcode.com/problems/jump-game-ii/)
45. Jump Game II #Array #Dynamic-Programming #Greedy #Two-Pointers
* Two pointers:
	* 先找出每個點可以到的最遠距離
	* 找出每次可以到的點裡面的最遠距離
	* 每找一次代表需要跳一次
	```python
	class Solution:
		def jump(self, nums: List[int]) -> int:
			nums[:] = [nums[i]+i for i in range(len(nums))]
			
			left, right, count = 0, 0, 0
			while right < len(nums)-1:
				count += 1
				left, right = right +1, max(nums[left:right+1])
			
			return count
	```

---
## [55. Jump Game](https://leetcode.com/problems/jump-game/)
55. Jump Game #Array #Dynamic-Programming #Greedy
* Greedy sol:
	* 想像是一台車子開車需要油
	* 每次移動都會消耗油，到下個點可以選擇要不要換這桶油
	```python
	class Solution:
		def canJump(self, nums: List[int]) -> bool:
			gas = 0
			for num in nums:
				if gas < 0:
					return False
				elif num > gas:
					gas = num
				gas -= 1
			
			return True
	```

test 
