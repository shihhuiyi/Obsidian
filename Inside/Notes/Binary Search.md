---
up:
  - "[[Data Structure and Algorithm]]"
  - "[[Array]]"
---
---
- 條件
	1. 必須是有序的
	2. 沒有重複的值，否則index不會是唯一
- Target的區間地義
	- 左閉右閉 $[left, right]$
		- mid大於target，代表target在左邊
		- target區間為左閉右閉，right更新為mid-1，讓right也包含target的區間
		```python
		while left <= right:
			if nums[mid] > target:
				left = mid -1
		```
		![[Pasted image 20241002221834.png]]
	- 左閉右開 $[left, right)$
		- target區間為左閉右開，right更新為mid，讓right不包含target的區間
		```python
		while left < right:
			if nums[mid] > target:
				left = mid
		```
		![[Pasted image 20241002221855.png]]

---
時間複雜度：O(log n)