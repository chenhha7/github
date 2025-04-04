

# 贷款数据字段说明

以下是贷款数据的各个字段及其对应的描述：

| 字段名称                | 描述                                                           |
|-------------------------|----------------------------------------------------------------|
| **id**                   | 贷款清单分配的唯一信用证标识                                      |
| **loanAmnt**             | 贷款金额                                                        |
| **term**                 | 贷款期限（年）                                                  |
| **interestRate**         | 贷款利率                                                        |
| **installment**          | 分期付款金额                                                    |
| **grade**                | 贷款等级                                                        |
| **subGrade**             | 贷款等级之子级                                                  |
| **employmentTitle**      | 就业职称                                                        |
| **employmentLength**     | 就业年限（年）                                                  |
| **homeOwnership**        | 借款人在登记时提供的房屋所有权状况                                |
| **annualIncome**         | 年收入                                                          |
| **verificationStatus**   | 验证状态                                                        |
| **issueDate**            | 贷款发放的月份                                                  |
| **purpose**              | 借款人在贷款申请时的贷款用途类别                                |
| **postCode**             | 借款人在贷款申请中提供的邮政编码的前3位数字                      |
| **regionCode**           | 地区编码                                                        |
| **dti**                  | 债务收入比                                                      |
| **delinquency_2years**   | 借款人过去2年信用档案中逾期30天以上的违约事件数                  |
| **ficoRangeLow**         | 借款人在贷款发放时的fico所属的下限范围                           |
| **ficoRangeHigh**        | 借款人在贷款发放时的fico所属的上限范围                           |
| **openAcc**              | 借款人信用档案中未结信用额度的数量                              |
| **pubRec**               | 贬损公共记录的数量                                              |
| **pubRecBankruptcies**   | 公开记录清除的数量                                              |
| **revolBal**             | 信贷周转余额合计                                                |
| **revolUtil**            | 循环额度利用率，或借款人使用的相对于所有可用循环信贷的信贷金额    |
| **totalAcc**             | 借款人信用档案中当前的信用额度总数                              |
| **initialListStatus**    | 贷款的初始列表状态                                              |
| **applicationType**      | 表明贷款是个人申请还是与两个共同借款人的联合申请                |
| **earliesCreditLine**    | 借款人最早报告的信用额度开立的月份                              |
| **title**                | 借款人提供的贷款名称                                            |
| **policyCode**           | 公开可用的策略代码=1新产品不公开可用的策略代码=2                |
| **n系列匿名特征**        | 匿名特征n0-n14，为一些贷款人行为计数特征的处理                   |

# 金融风控预测类常见评估指标

## 1. KS (Kolmogorov-Smirnov)

KS统计量由两位苏联数学家A.N. Kolmogorov和N.V. Smirnov提出。在风控中，KS常用于评估模型区分度。区分度越大，说明模型的风险排序能力（ranking ability）越强。

- **K-S曲线与ROC曲线的区别**：
  - ROC曲线将真正例率和假正例率作为横纵轴。
  - K-S曲线将真正例率和假正例率都作为纵轴，横轴则由选定的阈值来充当。

**公式**：

$`KS = max(TPR - FPR)`$



- **KS值的不同情况**：
  - 一般情况下，KS值越大，模型的区分能力越强，但也不是越大模型效果就越好。如果KS过大，模型可能存在异常。因此，若KS值过高，可能需要检查模型是否过拟合。

| KS（%）   | 好坏区分能力           |
|-----------|------------------------|
| 20以下    | 不建议采用             |
| 20-40     | 较好                   |
| 41-50     | 良好                   |
| 51-60     | 很强                   |
| 61-75     | 非常强                 |
| 75以上    | 过于高，疑似存在问题   |

## 2. ROC


## 3. AUC

```python
import pandas as pd
