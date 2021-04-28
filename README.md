# Capstone Project_Anomaly & Fraud detection credit card from customer's behaviors

____________________________________________________________________________________________________________________

# Problem Statement

1. Which factors or behavior of fraudulent customer.
2. To classify and predict new transaction automatically.
3. Which models are the best efficient to predict fraud.
____________________________________________________________________________________________________________________

# Data Description

| Features | Description |
|---|---|
|TransactionDT |Timedelta from a given reference datetime. |
|TransactionAMT |Transaction payment amount in USD. |
|ProductCD |Product code, the product for each transaction. |
|Card1 - Card6 |Payment card information, such as card type, card category, issue bank, country, etc. |
|Addr |Address |
|Dist |Distance |
|P_ and (R__) emaildomain |Purchaser and recipient email domain |
|C1-C14 |Counting, such as how many addresses are found to be associated with the payment card, etc. The actual meaning is masked. |
|D1-D15 |Timedelta, such as days between previous transaction, etc. |
|M1-M9 |Match, such as names on card and address, etc. |
|Vxxx |Vesta engineered rich features, including ranking, counting, and other entity relations. |

Due to this data has many features so, I will use some feature for exploring the data.

**Features >> TransactionAmt, ProductCD, card1-card6, P_emaildomain, DeviceType**

**Class >> isFraud**
____________________________________________________________________________________________________________________


# Evaluation Model

| Model | TP | TN | FP | FN | Accuracy | Misclassification | Precision | Recall | Specificity |
|---|---|---|---|---|---|---|---|---|---|
| AutoEncoder | | | | | | | | | |
| Thres 90.0% | 1,894 | 103,885 | 10,072 | 2,257 | 89.56% | 10.44% | 15.83% | 45.63% | 91.16% |
| Thres 96.5% | 1,147 | 110,997 | 2,960 | 3,004 | 94.95% | 5.05% | 27.93% | 27.63% | 97.40% |
| Thres 99.0% | 546 | 113,326 | 631 | 3,605 | 96.41% | 3.59% | 46.39% | 13.15% | 99.45% |
| Thres 99.5% | 332 | 113,698 | 259 | 3,819 | 96.55% | 3.45% | 56.18% | 8.00% | 99.77% |
| Thres 99.9% | 82 | 113,920 | 37 | 4,069 | 96.52% | 3.48% | 68.91% | 1.98% | 99.97% |
| Decision Tree | 2,186 | 105,715 | 2,186 | 1,965 | 91.36% | 8.64% | 20.96% | 52.66% | 92.77% |
| Random Forest | 2,684 | 109,095 | 4,862 | 1,467 | 94.64% | 5.36% | 35.57% | 64.66% | 95.73% |
| Gradient Boosting | 2,780 | 98,369 | 15,588 | 1,371 | 85.64% | 14.4% | 15.14% | 66.97% | 86.32% |
____________________________________________________________________________________________________________________

# Conclusion

1. Fraudulent transactions spend a little money but many times.

2. The transaction with product C, Discover card, credit card, Microsoft email and use a mobile have more probable to be a fraudulent transactions.

3. The best model to predict probability of fraud or not fraud for this data set is Gradient Boosting.

4. Each company has the different criteria to detect fraud so, we can adjust the suitable threshold from the model’s prediction.


