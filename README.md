# SQL-PBI_Inventory_Controlling

## I. Introduction
### 1. Business question
   
The sales department wants to know the overview of inventory status and look up the product inventory by category and location to come up with an appropriate sales and marketing strategy.

### 2. Dataset

Dataset: adventureworks2019 (public Google BigQuery dataset)

Dataset dictionary: Please reach file "Data Dictionary" attached above

Dataset Schema: https://i0.wp.com/improveandrepeat.com/wp-content/uploads/2018/12/AdvWorksOLTPSchemaVisio.png?ssl=1

Dataset access:

- Log in to your Google Cloud Platform account and create a new project.
- Navigate to the BigQuery console and select your newly created project.
- In the navigation panel, select "Add Data" and then "Star a project by name".
- Enter the project name "adventurework2019"

## II. Apply design thinking mindset
### 1. Empathize
<img width="916" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/e0175a4c-5f2d-4af4-a135-0ec33b6c564c">

### 2. Define point of view
<img width="607" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/16d8591e-0449-42e8-9aa1-6ee5a78129af">

### 3. Ideate
<img width="607" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/700e3dee-5c0f-468e-97eb-b63b0ac826df">

### 4&5. Prototype and review

<img width="606" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/be5b809f-e73a-4950-bfb9-15771fc5558a">

## III. Main Process

### 1. Extract data with Google BigQuery
   
Output total produced quantity and total sold quantity by month/year/quarter (Fact_Built_&_Sold table)
<img width="626" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/b605e89e-65b4-477a-b6db-e75eb0385ede">

<img width="633" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/0cd10aff-3076-4a96-bbe8-a0df329e253d">


Output product ID, product name, sub-category, category (dim_category table)

<img width="626" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/750a0492-4d2e-4852-809b-dcf2f2b23854">

Output total inventory quantity by product ID (dim_inventory_by_product table)

<img width="629" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/c6207d62-4b49-4483-a3e1-87b93e4ad9ab">

### 2. Connect data to PBI and modelling

- Connect queries above and available tables of dataset to PBI
- Modelling

<img width="611" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/b8e4c238-a742-475c-ad2a-da87a7093a08">

### 3. Build dashboard

- Using DAX to create measures and calculated columns
- Build 2 report pages

Overview of inventory by time/location/product

<img width="611" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/b87b89f7-406e-41fa-a59f-427b33bbb2cd">

Look up inventory status of each product

<img width="608" alt="image" src="https://github.com/ngocnguyen13400/ngocnguyen/assets/164152947/9f7b2806-7627-4e40-8802-e8bfa47ab97c">

## IV. Insights

### 1. Revenue - Inventory overview
   
- Revenue tends to increase steadily from 2011 to the end of 2013. Every year, revenue usually peaks in the third quarter and gradually declines in the fourth quarter.
- Stock to sales ratio (average inventory value/sales) tends to increase gradually => Inventory efficiency is decreasing

### 2. Revenue - Inventory by Category

- Current revenue is only recorded from 2 categories: Bikes and Components
- The largest revenue comes from the Bikes category at $145M (88%), 7 times more than the Components category
- The Bikes category has the largest inventory value of 24M (70%), nearly 4 times higher than the Components industry (9M).
- Components have a higher proportion of inventory value than revenue => Overstocking

### 3. Revenue - Inventory by Subcategory

- Top 3 Subcategory belong to Bikes category, the rest belong to Components category
- Subcategory Road Bikes, Mountain Bikes, Touring Bikes has a ratio of inventory value to sales ranging from 15 to 21%, higher than Mountain Frames 37%
- The highest is Subcategory Wheels (210%) => Overstocking

### 4. Revenue - Inventory by Product

- Top 2 products in the Components category, the rest in the Bikes category
- These products have a high inventory-to-sales ratio: HL Mountain Frame - Black, 38 (127%), HL Mountain Frame - Silver, 38 (61%), Road-150 Red, 44 (51%) => Overstocking
- Currently, the company has 69 types of products with inventory below the safe level -> Understocking. In which, most products belong to the Other category (55 products).

### 5. Inventory by Location
   
- Locations that are occupying the highest amount of inventory are Subassembly (95K units) and Miscellaneous Storage (83K units), but have low total inventory values (3.3M and 1.5M, respectively) => Store many items that are low-value
- Location Final Assembly and Finished Goods Storage, although not having a high inventory volume (20K and 17K, respectively), have the highest total inventory value (13.6M and 12.2M respectively) => Store items that are high-value.

## V. Recommendations

- Adjusting the amount of inventory to increase or decrease in proportion to the rate of revenue fluctuations, with an increase in the third quarter of each year and a gradual decrease beginning in the fourth quarter.
- Research more about the reason the stock-to-sales ratio tends to rise in order to find solutions to lower inventory costs.
- Make a new marketing plan for Accesories, clothing, and Other categories because they are currently not bringing in revenue.
- Focus on promoting sales of HL Mountain Frame - Black, 38, HL Mountain Frame - Silver, 38 and Road-150 Red, 44 products, as well as products in Subcategory Wheels to resolve inventory backlog
- Notify and check with the production and purchasing departments about the products that are currently out of stock and adjust the Safety Stock level to suit the profitability of each product line.
- Many items are out of stock, so it is recommended to collect more opportunity cost data when an item is out of stock, which can be used to control and forecast future sales.














