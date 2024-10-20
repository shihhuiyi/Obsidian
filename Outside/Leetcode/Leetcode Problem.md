
## [45. Jump Game II](https://leetcode.com/problems/jump-game-ii/)
45. Jump Game II #Medium #Array #Dynamic-Programming #Greedy #Two_Pointers
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
55. Jump Game #Medium #Array #Dynamic-Programming #Greedy
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

---
## [151. Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/)
151. Reverse Words in a String #Medium #Two_Pointers #String 
* 直接用空格拆開再反序組回去
* 如果有多個空格的話，會有空值出現，要把空值移除掉
```python
class Solution:
    def reverseWords(self, s: str) -> str:
        s = [i for i in s.split(" ") if i]
        
        return " ".join(s[::-1])
```

---
## [238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)
238. Product of Array Except Self #Medium #Array #Prefix_Sum
* 自己以外的值相乘 = 左邊相乘 * 右邊相乘
```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * len(nums)
        
        left = 1
        for i in range(len(nums)):
            res[i] *= left
            left *= nums[i]

        right = 1
        for i in range(len(nums)-1, -1, -1):
            res[i] *= right
            right *= nums[i]
            
        return res
```
 
---
## [334. Increasing Triplet Subsequence](https://leetcode.com/problems/increasing-triplet-subsequence/)
334. Increasing Triplet Subsequence #Medium #Array #Greedy 
* 用兩個變數紀錄前兩個較小的
* 如果都滿足的話代表第三個也找到了
```python
class Solution:
    def increasingTriplet(self, nums: List[int]) -> bool:
        first = second = float("inf")
        for n in nums:
            if n <= first:
                first = n
            elif n <= second:
                second = n
            else:
                return True
        
        return False
```
---
## [345. Reverse Vowels of a String](https://leetcode.com/problems/reverse-vowels-of-a-string/)
345. Reverse Vowels of a String #Easy #Two_Pointers #String 
* 用stack儲存所有的母音
* 再把遇到的母音組裝回去
```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowels = "AEIOUaeiou"
        stack = [i for i in s if i in vowels]
        
        return "".join([stack.pop() if i in vowels else i for i in s])
```

---
## [605. Can Place Flowers](https://leetcode.com/problems/can-place-flowers/)
605. Can Place Flowers #Easy #Array #Greedy 
* The men's toilet problem
* 要種植的數量是0的話一定可以
* 如果現在左邊右邊都是空的就可以種
```python
class Solution:
    def canPlaceFlowers(self, flowerbed: List[int], n: int) -> bool:
        if n == 0: return True

        for i in range(len(flowerbed)):
            if flowerbed[i] == 0 and (i == 0 or flowerbed[i-1] == 0) and (i == len(flowerbed)-1 or flowerbed[i+1] == 0):
                flowerbed[i] = 1
                n -= 1
            if n == 0: return True

        return False
```

---
## [1071. Greatest Common Divisor of Strings](https://leetcode.com/problems/greatest-common-divisor-of-strings/)
1071. Greatest Common Divisor of Strings #Easy #Math #String 
* 可以透過合併字串判斷是否由同樣的字串組成
* 找出最大公因數就可以知道是由哪些字串組成的
* 輾轉相除法 (歐基里德算法)
	* 用大的數去除於數
```python
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        if str1 + str2 != str2 + str1: return ""

        # 輾轉相除法，找最大公因數
        a, b = len(str1), len(str2)
        while b != 0:
            a, b = b, a%b

        return str1[:a]
```

---
## [1431. Kids With the Greatest Number of Candies](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/)
1431. Kids With the Greatest Number of Candies #Easy #Array 
* 找出最大值
* 迴圈判斷加上額外糖果能不能大於最大值
```python
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        max_candy = max(candies)

        return [i + extraCandies >= max_candy for i in candies]
```

---
## [1768. Merge Strings Alternately](https://leetcode.com/problems/merge-strings-alternately/)
1767. Merge Strings Alternately #Easy #String #Two_Pointers 
* 先用迴圈把最小長度的交互合併
* 再把較長字串剩餘的部分合併
```python
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        res = ""
        curr = 0
        while curr <= len(word1)-1 and curr <= len(word2)-1:
            res += word1[curr]
            res += word2[curr]
            curr += 1

        if curr <= len(word1)-1:
            res += word1[curr:]
        else:
            res += word2[curr:]

        return res
```

---
