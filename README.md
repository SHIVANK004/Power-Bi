# Power-Bi
The 7 pillars for Mastering Power BI:

1) Extraction
2) Transformation
3) Modeling
4) Calculation
5) Visualization
6) Distribution
7) Automation

 
- DAX: Data Analysis eXpressions
- Filter context: 
	- the combination of all filters that are applied on the report
	- They propagate through the relationships
- Row context:
	- when we create a calculated column or when we use iterative funcions (like SUMX)
	- There is a current row being iterated
	- Iterative processs

- CALCULATE function: it is the only that can modify the evulation context
	- Syntax: CALCULATE( <expression>, Filter 1, Filter 2, ... )
  
 # 1) Extraction
  
  Where does data come from?
Generaly from an OLTP database. But the way we connect to this data can vary across organizations, mainly due to security reasons.

How do you get the data you work with today?

	1) Connecting directly in the transactional database (OLTP)
	2) Connecting to a Data Warehouse (DW)
	3) Through an Excel file connected to the database
	4) Extracting reports from the ERP system
	5) Filling out spreadsheets manually

 
 # 2) Transformation

- What is the correct structure of a table?
	- Always columnar 
	- Each column must represent a unique type of information

- When you deal with real data, it is usually messy and dirty
	- So it is extremely important to TRANSFORM it before loading into the model

- Power Query is our best friend for this. It is the tool to prepare, transform and put the data into the right shape
- Even better: you do this only once, because it automates all your ETL process

# 3) Modeling

- We always have to think about two types of table:

	1) Dimension tables: 
		- Describe business entities, the things in our model.
		- Lookup tables, the What, When, Where, Who.
		- They store the perspectives, the attributes of the entities, their descriptions.
		- Must contain a key column that acts as a unique identifier.
		- They are used to filter and group the values you want to analyze
		- You use them usualy in the axis of the visuals and on slicers.
		- Usually short but wide (not so many rows and lots of columns).
		- Ex: products, customers, suppliers, accounts, etc

	2) Fact tables:
		- Data table, the transactions, events that happen over time.
		- Usually there is a date associated to an event.
		- Contains dimension key columns that relate to dimension tables, and numeric columns.
		- Can be very tall (and grow over time) but usualy thin (lots of rows and not so many columns).
		- Ex: sales orders, stock balances, financial transactions, temperatures, etc.

# 4) Calculation

- DAX: Data Analysis eXpressions

- We can create columns, measures or tables with DAX
	1) Columns: consume memory and are static calculations. Use it for descriptive information on the Axis and Filters.
	2) Measures: are dynamic and consume only CPU, because they are calculated on the fly. Use always for Math (numbers that you place in the Values of the visuals);
	3) Tables: not used often. It is better to create them in Power Query, with exception to the Date table.

Where is the Power of DAX? 1, 2 or 3?
	2) Measures

- Filter context:
	- The combination of all filters that are applied on the report
	- They propagate through the relationships and provide a subset of the original table, a filtered table

- CALCULATE function: it is the only that can modify the evulation context
	- Syntax: CALCULATE( <expression>, Filter 1, Filter 2, ... )
	
- Row context:
	- when we create a calculated column or when we use iterative funcions (like SUMX)
	- There is a current row being iterated
	- Iterative processs

# 5) Visualization

- What is Data Storytelling?
	-> The power of building a narrative around a set of data to help convey the meaning of that data in a powerful and compelling fashion 
		https://tdwi.org/portals/what-is-data-storytelling-definition.aspx
	-> In other words, to guide your audience smoothly through the analysis.
	-> A dashboard is like a joke. If you have to explain that's because it was not good.

- Recomendations:
	1) Identify your audience
		- Ask how a dashboard will be used and design for next step actions
		- What information does the reader need to be successful?
		- How much detail does the reader need?
	2) Draw a sketch
		- Good design should tell a story with data that does not become overwhelming with way too much information, clutter or noise. 
		- Limit content to fit entirely on one screen.
		- Keep your dashboard simple with only a 3 to 5 key values, charts, or tables. Avoid putting too much information on a dashboard.
		- If detail tables are needed, place them on the bottom of the dashboard
	3) Choose the right visuals
	4) Choose the right theme and keep consistency
		- https://color.adobe.com/explore
5) Create a background (WOW effect)
6) Use icons and images to add context 
	- https://logomakr.com
7) Align all visuals properly
8) Use references to get inspiration
9) Use visualization features from Power BI (tooltip, drill-through, bookmarks...)


