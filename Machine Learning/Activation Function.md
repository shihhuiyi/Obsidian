### 激活函數
* 進行非線性轉換
* 常見激活函數
	1.	Sigmoid 函數：
		•	定義： $\sigma(x) = \frac{1}{1 + e^{-x}}$ 
		•	範圍： $(0, 1)$ 
		•	優點：輸出範圍有限，適合處理二分類問題。
		•	缺點：容易造成梯度消失，尤其是對於深層網絡。
	2.	Tanh 函數：
		•	定義： $\tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$ 
		•	範圍： $(-1, 1)$ 
		•	優點：比 Sigmoid 函數表現更好，因為它的輸出範圍是對稱的，有助於減少梯度消失問題。
		•	缺點：仍然可能會遇到梯度消失問題。
	3.	ReLU（Rectified Linear Unit）：
		•	定義： $\text{ReLU}(x) = \max(0, x)$ 
		•	範圍： $[0, \infty)$ 
		•	優點：簡單計算，能夠加速訓練過程，並且在深層網絡中較少出現梯度消失問題。
		•	缺點：在訓練過程中，部分神經元可能會被激活為 0，導致神經元”死亡”（稱為 Dying ReLU 問題）。
	4.	Leaky ReLU：
		•	定義： $\text{Leaky ReLU}(x) = \begin{cases} x & \text{if } x > 0 \\ \alpha x & \text{if } x \leq 0 \end{cases}$ 
		•	範圍： $(-\infty, \infty)$ 
		•	優點：在負區間也有斜率，能夠減少 Dying ReLU 問題。
		•	缺點：需要選擇合適的斜率 $α$。
	5.	ELU（Exponential Linear Unit）：
		•	定義： $\text{ELU}(x) = \begin{cases} x & \text{if } x > 0 \\ \alpha(e^x - 1) & \text{if } x \leq 0 \end{cases}$ 
		•	範圍： $(-\alpha, \infty)$ 
		•	優點：在負區間有平滑的非線性，能夠解決 Dying ReLU 問題，並且有助於加快訓練速度。
		•	缺點：計算較為複雜。
	6.	Softmax 函數：
		•	定義： $\text{Softmax}(x_i) = \frac{e^{x_i}}{\sum_{j} e^{x_j}}$ 
		•	範圍： $(0, 1)$ （每個輸出值的總和為 1）
		•	優點：常用於多分類問題的輸出層，能夠將網絡的輸出轉化為概率分布。
		•	缺點：不適合用於隱藏層。
