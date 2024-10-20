---
up:
  - "[[Data Structure and Algorithm]]"
  - "[[Array]]"
---
---
- 通過快慢指針==在一個迴圈中完成兩個迴圈的工作==
- 應用:
	- 刪除元素
		- 慢指針: 更新的新位置
		- 快指針: 尋找新元素
		![[Pasted image 20241002232151.png]]
	- 有序array平方的排序
		- 最大的會在兩側
		- 指針放在兩端
			![[Pasted image 20241003214747.png]]
	- 反轉字符串
		- 用list[::-1]就沒考的意義了
		- 用two pointers做交換
- 變形:
	- [[Sliding Window]]
- 解題技巧：
	- n sum
		- 透過two pointer把兩個迴圈變成一個回圈
		- 其他的迴圈照跑
		- 3sum就1個回圈+two pointers
		- 4sum就2個回圈+two pointers

---
時間複雜度：O(n)