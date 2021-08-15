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

 
  2) Transform

- What is the correct structure of a table?
	- Always columnar 
	- Each column must represent a unique type of information

- When you deal with real data, it is usually messy and dirty
	- So it is extremely important to TRANSFORM it before loading into the model

- Power Query is our best friend for this. It is the tool to prepare, transform and put the data into the right shape
- Even better: you do this only once, because it automates all your ETL process


