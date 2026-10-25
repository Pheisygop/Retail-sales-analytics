
# Retail Sales Analytics

A Power BI portfolio project analysing real retail transactions to understand sales trends, product performance and highest-value customers.
## Report Preview

![Sales Overview](screenshots/sales_overview.png)

[View the PDF report](reports/Retail_Sales_Analytics.pdf)

[Download the Power BI report](powerbi/Retail_Sales_Analytics.pbix)

## Business Questions

- How do sales change over time?
- Which countries generate the most sales?
- Which products lead before and after cancellations?
- Which identified customers contribute the most sales?

## Tools Used

- Power BI Desktop for modelling and interactive reports
- Power Query for data preparation
- DAX for business measures

## Dataset

UCI Online Retail: 541,909 transaction lines covering
1 December 2010 to 9 December 2011.

All monetary values are in GBP (£).

## Report Pages

1. Sales Overview
2. Product Analysis
3. Customer Analysis
4. About the Data

## Key Results

| Metric | Value |
|---|---:|
| Gross Sales Value | £10,655,622.48 |
| Cancellation Value | £896,812.49 |
| Sales After Cancellations | £9,758,809.99 |
| Sales Orders | 19,959 |
| Average Order Value | £533.88 |

Results represent the full period with no country selection.

## Findings

- November 2011 recorded the highest monthly gross sales.
- The Netherlands led gross sales outside the United Kingdom.
- REGENCY CAKESTAND 3 TIER led product descriptions by sales
  after cancellations at £164,762.19.
- PAPER CRAFT, LITTLE BIRDIE generated £168,469.60 in gross
  sales, offset by the same aggregate cancellation value.
- Customer 14646 led identified customers with £279,489.02
  in sales after cancellations across 73 sales orders.

## Data Preparation and Modelling

- Assigned appropriate data types to identifiers, dates,
  quantities and prices.
- Created line amounts from Quantity × UnitPrice.
- Flagged cancellation invoices, missing customer IDs and
  bad-debt adjustments.
- Created a Calendar table related to the invoice date.
- Retained source rows and applied business rules through
  measures and report filters.

## Measure Definitions

- Gross Sales Value: line amounts with positive quantity
  and price, excluding cancellation invoices and bad-debt
  adjustments.
- Cancellation Value: the positive magnitude of negative
  line amounts on cancellation invoices with positive prices,
  excluding bad-debt adjustments.
- Sales After Cancellations: Gross Sales Value minus
  Cancellation Value.
- Sales Orders: distinct invoices meeting the gross sales rules.
- Average Order Value: Gross Sales Value divided by Sales Orders.

## Limitations

- December 2011 contains only 1–9 December and should not be
  compared directly with complete months.
- CustomerID is missing on 135,080 transaction lines (24.93%).
  These remain in overall sales analysis but are excluded
  from customer rankings.
- Product rankings group by Description, which can vary for
  the same StockCode.
- Product Analysis excludes POSTAGE, DOTCOM POSTAGE and Manual.
  Other operational entries may remain.
- Sales After Cancellations is not a profit measure or a
  complete accounting revenue calculation.
- Static findings describe the full period and all countries;
  they do not change when slicers are used.

## Project Files

- powerbi/ — editable Power BI report
- reports/ — PDF report
- screenshots/ — report previews

## How to View

Open the PDF in the reports folder for a static overview.

For interactive analysis, open
powerbi/Retail_Sales_Analytics.pbix in Power BI Desktop.

To refresh the report, download the source workbook and update
its file location under Transform data → Data source settings.
The original local file path will differ on another computer.

## Author

Pheisel Gopito![alt text](image.png)