# UPI Transaction Analysis (Power BI)
A Power BI report on 2024 UPI transactions. It shows how transaction amounts and remaining balances change month by month, and lets you slice the data by bank, city, device, payment method, age group and more.
## Preview

| Amount by month | Balance by month |
|---|---|
| <img width="1127" height="640" alt="Dashboard_2" src="https://github.com/user-attachments/assets/2036541b-a5ae-4230-afaf-d4ca7d17e54f" /> |
| <img width="1132" height="642" alt="Dashboard_1" src="https://github.com/user-attachments/assets/982af9cc-3150-4850-af1d-ce9ab3cb3f01" /> |
| <img width="1121" height="632" alt="Dashboard_3" src="https://github.com/user-attachments/assets/4d23076c-eaa9-4a62-bdaf-fddff5042bac" /> |
| <img width="960" height="542" alt="Dashboard_4" src="https://github.com/user-attachments/assets/9f50d250-6721-4661-b4d6-6255cb3fc64f" />  |
| <img width="1127" height="637" alt="Dashboard_P2" src="https://github.com/user-attachments/assets/ec8198cf-2586-4dbb-820f-53f49c92e291" /> |

## Data Model
|<img width="1475" height="740" alt="Data_Model_UPI" src="https://github.com/user-attachments/assets/5c6da26c-b743-4479-bc25-6e7aaab25060" /> 


## What's in the report

**Page 1: Monthly trends**
- Transaction amount by month (line and column views)
- Remaining balance by month (line and column views)
- 4 bookmark buttons to switch between the views

**Page 2: City, currency and month**
- Matrix of amount and remaining balance by city, currency and month
- Conditional colours to spot high and low values quickly

**Controls**
- 10 slicers: BankNameSent, BankNameReceived, City, DeviceType, Gender, Age_Groups, MerchantName, PaymentMethod, Purpose, TransactionType
- Currency filter applied on all pages
- Bookmarks and the Selection pane to control which visual shows

## Data

- One table: `UPI_Transaction`
- About 20,000 transactions in INR, USD, EUR and GBP
- Main columns: Amount, RemainingBalance, TransactionDate, City, Currency, BankNameSent, BankNameReceived, DeviceType, Gender, MerchantName, PaymentMethod, Purpose, TransactionType, Status
- Calculated column: `Age_Groups` (groups CustomerAge into age ranges)
- Source: *add your dataset source here*

## DAX used

**Age_Groups** (calculated column): groups customers into three age bands so they can be used in a slicer.

```DAX
Age_Groups =
SWITCH(
    TRUE(),
    UPI_Transaction[CustomerAge] <= 25, "Up to 25",
    UPI_Transaction[CustomerAge] <= 35, "26-35",
    "36 and above"
)
```

Other totals use Power BI's default sum on `Amount` and `RemainingBalance`.

## Key findings

- Monthly amounts stay between 1.60M (August) and 1.71M (May).
- Remaining balance is highest in June (8.54M) and lowest in May (8.22M).

## Limitations

- The data has four currencies. Amounts are not converted, so trends are meaningful when one currency is selected.
- Remaining balance is summed by month, which shows a trend but is not a true account balance.
- The dataset looks like sample data, so city-level results should not be read as real business performance.

## Possible improvements

- Add a Date table for time intelligence
- Convert all amounts to one currency
- Use average or last balance per account instead of a sum
- Add analysis of failed transactions using the `Status` column

## How to open

1. Download `UPI_Transaction_Project.pbix`
2. Open it in Power BI Desktop

## Tools

Power BI Desktop, DAX, Power Query

## Author

Umesh Sakpal
Power BI Developer and Data Analyst
[GitHub](https://github.com/Sakpal23) · umeshsakpal14@gmail.com
