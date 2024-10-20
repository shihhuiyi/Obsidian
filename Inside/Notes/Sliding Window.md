---
up:
  - "[[Data Structure and Algorithm]]"
  - "[[Array]]"
  - "[[Two Pointers]]"
---
---
- 為Two Pointers的一種變形
- 不斷調整子序列的開始和終點，達到我們要的效果
	- 窗口內是什麼？
	- 怎麼移動起始位置？
	- 怎麼移動終點位置？
	![[Pasted image 20241004213904.png]]

---
時間複雜度：O(n)
雖然是用兩個迴圈是去跑，但是每個元素只會被操作2次，所以複雜度是O(2n)，也就是O(n)