---
up:
  - "[[Data Structure and Algorithm]]"
---
---
- 一種通過指針串連在一起的線性結構
- 節點包含數據域和指針域
	- 數據域
		- 存放數據
	- 指針域
		- 存放指向下個節點的指針
		- 入口節點稱為head
		- 最後一個節點會指向null	
		![[Pasted image 20241008202337.png]]
- 鍊表類型
	- 單鍊表
		- 指針只能指向下個節點
	- 雙鍊表
		- 有兩個指針
		- 一個指向上個節點
		- 一個指向下個節點
		- 可以向前向後查詢
		![[Pasted image 20241008202652.png]]
	- 循環鍊表
		- 鍊表頭尾相連
		- 可以解決約瑟夫環問題
		![[Pasted image 20241008202756.png]]
- 儲存方式
	- 內存不是連續分佈的，是通過指針指向下個節點，跟Array不同
	![[Pasted image 20241008203022.png]]
- 操作方式
	- 都是透過修改指針來改變
	- 新增
		![[Pasted image 20241008203325.png]]
	- 刪除
		![[Pasted image 20241008203315.png]]
		- 要移除head只要把head往後移一個
			![[Pasted image 20241008203734.png]]
			- 但這樣寫法會比較麻煩，不能全部都用上面通用的方式
			- 可以透過把head改為dummy node來解決
				![[Pasted image 20241008203917.png]]
- Linked List v.s Array
	![[Pasted image 20241008203407.png]]
- 解題技巧
	- 常使用dummy head
	- 常搭配two pointers
		- 翻轉
		- 交換順序
		- 刪除倒數第幾個元素