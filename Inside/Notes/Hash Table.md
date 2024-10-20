---
up:
  - "[[Data Structure and Algorithm]]"
---
---
- 透過hash function把key映射到value
	- ![[Pasted image 20241009232148.png]]
	- 哈希碰撞
		- 遇到兩個對應到同個點
		- 拉鍊法
			![[Pasted image 20241009232302.png]]
		- 線性探測法
			- table size 一定要大於 data size
			![[Pasted image 20241009232337.png]]
- 常見hash table架構
	- set
	- map