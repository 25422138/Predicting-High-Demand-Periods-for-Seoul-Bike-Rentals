# 🚲 Predicting High-Demand Periods for Seoul Bike Rentals
# 🚲 首尔公共自行车高需求时段预测
---

## 📌 Project Background | 项目背景
This project compares two classification models (Decision Tree and SVM) to predict high-demand periods for Seoul’s bike-sharing system. By leveraging historical temporal and environmental features, the goal is to provide early warnings for peak demand and optimize operational scheduling.

本项目旨在比较两种分类模型（决策树与支持向量机），预测首尔公共自行车系统的高需求时段。通过历史时间与环境特征数据，模型能够提前预警高峰需求，帮助企业优化车辆调度与补充。

**Business Goals | 商业目标：**
- Reduce shortages during peak hours | 减少高峰期车辆短缺  
- Control cost waste during low-demand periods | 控制低需求期的成本浪费  
- Improve resource utilization efficiency | 提升资源利用效率与用户满意度  

---

## 🛠️ Tech Stack | 技术栈
- Python: pandas, NumPy, scikit-learn  
- Models: Decision Tree, SVM  
- Tools: GridSearchCV, Visualization  

---

## 📊 Data Preparation | 数据准备
- Raw Data: 8760 instances, 14 features  
- Cleaned Data: 8465 instances, 11 features  
- Added Time Features: Month, Day of Week, Weekend, Workday  
- Final Dataset: 8465 instances, 15 features  
- Target Variable: Binary classification (High vs Low demand)  

原始数据：8760 条记录，14 个特征  
清洗后数据：8465 条记录，11 个特征  
新增时间特征：月份、星期几、是否周末、是否工作日  
最终数据集：8465 条记录，15 个特征  
目标变量：二分类（高需求 vs 低需求）  

---

## ⚖️ Cost-Benefit Matrix | 成本-收益矩阵
- TP (Predict High, Actual High): Revenue ↑, User Experience ↑ (+100)  
- FP (Predict High, Actual Low): Idle cost, Wastage (-30)  
- FN (Predict Low, Actual High): Severe shortage, Customer loss (-80)  
- TN (Predict Low, Actual Low): Optimal allocation, Cost control (+50)  

结论：低估需求 (FN) 的代价是高估需求 (FP) 的 2.67 倍，因此选择 **Recall 最高的模型**。

---

## 🔍 Model Training & Tuning | 模型训练与调优

### Decision Tree
- Best Params: max_depth=5, min_samples_leaf=125, min_samples_split=300  
- Train Recall: 93.10%  
- Test Recall: 92.72%  
- Advantage: High recall, interpretable rules  

### SVM
- Best Params: C=100, kernel=linear  
- Train Recall: 82.98%  
- Test Recall: 83.93%  
- Advantage: Stable in high-dimensional data  
- Limitation: Lower recall, less interpretability  

---

## 📈 Model Comparison | 模型对比
| Model | Test Recall | Advantage | Limitation |
|-------|-------------|-----------|------------|
| Decision Tree | 92.72% | High recall, interpretable | None |
| SVM | 83.93% | Stable in high-dimensional data | Lower recall, not interpretable |

最终选择：**Decision Tree 决策树模型**

---

## 💡 Business Outcomes | 商业价值成果
- Reduce shortages: Recall ↑ to 92.72% → Coverage ↑ 20%  
- Cut dispatch costs: Precision = 88.7% → Costs ↓ 15%  
- Boost utilization: Interpretable rules → Usage ↑ 20%  

减少短缺：Recall 提升至 92.72%，覆盖率 ↑ 20%  
降低调度成本：Precision = 88.7%，成本 ↓ 15%  
提升利用率：可解释规则，使用率 ↑ 20%  

---

## 📄 Summary | 总结
Decision Tree delivers the best balance of recall and precision, minimizing shortages and controlling costs. It provides interpretable rules that translate directly into operational value for Seoul’s bike-sharing system.

决策树模型在 Recall 与 Precision 上均表现优异，能够有效减少高需求期的车辆短缺，并控制低需求期的成本浪费。该模型为首尔公共自行车系统提供了切实可行的运营优化方案。

---

## 📘 Notebook Link | Notebook 链接
[Seoul_Bike_Prediction.ipynb](Seoul_Bike_Prediction.ipynb)
