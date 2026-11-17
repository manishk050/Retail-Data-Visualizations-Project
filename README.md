# BITS Retail Performance & Profitability Analysis

An end-to-end retail data analysis and visualization project using Python and Power BI. The project combines three annual transaction files with product and customer master data, validates and prepares the data, and presents the results in an interactive one-page dashboard.

## Project overview

The analysis covers retail orders from 2024 to 2026 and explores sales performance, profitability, regional results, product contribution, discount patterns and customer segments.

The final prepared dataset contains **1,310 transaction records and 14 columns**, covering **220 customers, 15 products, 5 regions and 3 product categories**.

## Business questions

The dashboard is designed to help answer the following questions:

1. **Sales trends:** How do sales change over time, and are there visible monthly patterns?
2. **Regional performance:** How do sales and profitability compare across regions?
3. **Product performance:** Which product categories and subcategories contribute most and least to sales and profit?
4. **Discount impact:** How do different discount levels relate to sales and profitability?
5. **Customer segments:** How do customer segments contribute to sales and overall performance?

## Tools used

- **Python:** data loading, inspection, cleaning, standardisation, merging and validation.
- **Pandas and NumPy:** data preparation and analysis.
- **Power BI Desktop:** data model, DAX measures, interactive visuals and dashboard design.
- **Jupyter Notebook:** documenting and running the preparation workflow.

## Project workflow

```text
Annual sales workbooks (2024, 2025, 2026) + master workbook
                         |
                         v
                Data understanding
                         |
                         v
          Data cleaning and standardisation
                         |
                         v
       Combine annual transaction datasets
                         |
                         v
       Join product and customer master data
                         |
                         v
             Data quality validation
                         |
                         v
          Export enriched dataset to CSV
                         |
                         v
             Power BI data model
                         |
                         v
       DAX measures, visuals and slicers
                         |
                         v
          Insights and recommendations
```

### 1. Data preparation with Python

The notebook follows these main steps:

- Loads the 2024, 2025 and 2026 retail transaction files.
- Inspects dataset dimensions, column names, data types, missing values and duplicates.
- Standardises data types for IDs, dates, numeric fields and categorical fields.
- Checks and removes duplicate records and rows with missing values in the annual transaction datasets.
- Combines the annual datasets into one transaction table.
- Loads the Product Master and Customer Master sheets.
- Standardises known category-label variations before joining the master data.
- Uses left joins to add product details and customer segments to each transaction.
- Validates unmatched product/customer IDs, row counts after merging, missing values, numeric business rules, categorical values and duplicate records.
- Exports the enriched dataset as a CSV file for Power BI.

### 2. Power BI dashboard

The Power BI report contains a single-page retail performance dashboard with KPI cards, analytical visuals and slicers.

**Key metrics displayed**

- Net Sales
- Profit After Shipping
- Profit Margin %
- Total Orders
- Average Order Value
- Loss-Making Orders %

**Main visuals**

| Analysis | Visual |
|---|---|
| Monthly performance | Monthly net sales and profit margin trend |
| Product contribution | Category and subcategory matrix showing sales, profit and margin |
| Regional performance | Comparison of net sales, profit after shipping and profit margin by region |
| Discount analysis | Sales, profit and margin across discount tiers |
| Customer analysis | Customer segment contribution |
| Product/order detail | Top products by profit, loss-making orders by subcategory and order quantity distribution |

**Dashboard filters**

- Date
- Category
- Customer Segment
- Region

The slicers allow the dashboard to be explored across different periods and business dimensions.

## Key observations from the dashboard

The dashboard provides a consolidated view of sales and profitability. A few visible patterns include:

- Technology is the largest category by net sales in the displayed results.
- Profit margin differs across categories and subcategories, so sales contribution alone does not indicate profitability.
- The displayed profit margin declines across higher discount tiers; the highest discount band shown has a negative margin.
- Regional results vary, making it useful to compare sales and profit together rather than ranking regions on sales alone.

These are descriptive observations from the dashboard. They show patterns in the supplied dataset and should not be interpreted as proof that discounts or other factors caused a change in profitability.

## Repository contents

```text
Retail-Data-Visualizations-Project/
|-- BITS_Retail_2024.xlsx              # Annual transaction data
|-- BITS_Retail_2025.xlsx              # Annual transaction data
|-- BITS_Retail_2026.xlsx              # Annual transaction data
|-- BITS_Retail_Master.xlsx            # Product and customer master sheets
|-- BITS_Retail_Student_Guide.xlsx      # Dataset/business guide
|-- Data Visualization (2).ipynb       # Python data preparation notebook
|-- retail_sales_enriched.csv          # Prepared dataset for Power BI
|-- Data Visualization.pbix            # Power BI dashboard
|-- Graded Assignment (1).pdf          # Assignment brief
|-- Data Visualization/                # Supporting screenshots and evidence
|-- README.md
```

## How to use this project

### Run the Python notebook

1. Clone or download this repository.
2. Install the required Python packages:

   ```bash
   pip install pandas numpy openpyxl matplotlib seaborn jupyter
   ```

3. Open the notebook:

   ```bash
   jupyter notebook "Data Visualization (2).ipynb"
   ```

4. Run the notebook cells in order. Keep the four Excel source workbooks in the repository root so the file paths in the notebook resolve correctly.
5. The notebook creates `retail_sales_enriched.csv` in the working directory.

### Open the Power BI dashboard

1. Open `Data Visualization.pbix` in Power BI Desktop.
2. If Power BI asks for the source file location, select `retail_sales_enriched.csv` from the repository folder.
3. Refresh the data if required.
4. Use the date, category, customer segment and region slicers to explore the report.

## Data notes

- The repository includes the supplied assignment workbooks and the prepared transaction-level CSV.
- The prepared dataset has 1,310 rows and 14 columns after combining the annual transactions and adding product and customer master attributes.
- The notebook includes checks for unmatched master IDs, merge row-count consistency, missing values, duplicate records and selected numeric business rules.
- The source files are included for project reproducibility. Please refer to the student guide and assignment brief for the original dataset definitions and task requirements.

## Project files

- [Python notebook](Data%20Visualization%20%282%29.ipynb)
- [Power BI dashboard](Data%20Visualization.pbix)
- [Prepared dataset](retail_sales_enriched.csv)
- [Assignment brief](Graded%20Assignment%20%281%29.pdf)
- [Supporting screenshots](Data%20Visualization/)

## Author

**Manish P Kharatamal**  
GitHub: [manishk050](https://github.com/manishk050)

---

This project was completed as a data visualization assignment and demonstrates a practical workflow from raw retail data preparation to an interactive Power BI dashboard.