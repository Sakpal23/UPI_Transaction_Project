# UPI Transaction Analysis (Power BI)
A Power BI report on 2024 UPI transactions. It shows how transaction amounts and remaining balances change month by month, and lets you slice the data by bank, city, device, payment method, age group and more.
## Preview

| Amount by month | Balance by month |
|---|---|
| ![Amount trend](screenshots/Dashboard_2.png) | ![Balance trend](screenshots/Dashboard_3.png) |

![City, currency and month matrix](screenshots/Dashboard_P2.png)

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

*Paste your measures here, with one line on what each does.*

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
