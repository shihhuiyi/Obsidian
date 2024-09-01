### 定義
* 分類問題的衡量指標
---
### 結構

|                      | 預測為正類 (Positive)    | 預測為負類 (Negative)    |
| -------------------- | ------------------- | ------------------- |
| **實際為正類 (Positive)** | True Positive (TP)  | False Negative (FN) |
| **實際為負類 (Negative)** | False Positive (FP) | True Negative (TN)  |
1.	Accuracy（準確率）：
	* $\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$
	* 表示模型預測正確的比例。
2.	Precision（精確率）：
	* $\text{Precision} = \frac{TP}{TP + FP}$
	* 表示在所有預測為正類的樣本中，實際為正類的比例。
3.	Recall（召回率）：
	* $\text{Recall} = \frac{TP}{TP + FN}$
	* 表示在所有實際為正類的樣本中，模型正確預測為正類的比例。
4.	F1 Score：
	* $\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$
	* 是精確率和召回率的調和平均，平衡了這兩者的性能。
5.	Specificity（特異度）：
	* $\text{Specificity} = \frac{TN}{TN + FP}$
	* 表示在所有實際為負類的樣本中，模型正確預測為負類的比例。