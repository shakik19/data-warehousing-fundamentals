## Additivity in Fact Tables: Making Sense of Your Data

In data warehouses, additivity refers to the ability to **sum** a fact table's measures across different dimensions. It essentially determines whether it makes logical sense to aggregate the values in your fact table based on various criteria. 

Here's a breakdown of the different types of additivity in fact tables:

**1. Additive Facts:**

These are the most desired and flexible type of fact. An additive fact can be **meaningfully summed** across **all dimensions** in the fact table.

* **Example:** In a sales data warehouse, the "Sales Amount" fact is likely additive. You can sum it up by product, customer, region, and time period to get meaningful insights like total sales per product category or total sales for a specific region over a quarter.

**2. Semi-Additive Facts:**

These facts can be added up across **some**, but not all, dimensions.

* **Example:** "Customer Balance" might be semi-additive. It makes sense to sum it up across customers for a specific point in time, but summing it across different time periods wouldn't be logical (a customer's balance at the end of January doesn't add up to their balance at the end of February).

**3. Non-Additive Facts:**

These facts cannot be meaningfully summed across **any dimension**.

* **Example:** Ratios (e.g., discount rate) or percentages (e.g., profit margin) are non-additive. Adding discount rates across products or customers wouldn't provide a meaningful result.

Here are some additional points to consider:

* Identifying additivity depends on the **business context**. What makes sense to sum up in one scenario might not be logical in another.
* Sometimes, you can **transform** non-additive facts into additive ones. For instance, you could store the actual sales amount and discount amount separately in the fact table, allowing you to sum the sales amount for an additive perspective.
* **Dimension hierarchies** can impact additivity.  For example, summing sales amount across subcategories within a product category would be additive, but summing across completely different product categories might not be as meaningful.

By understanding the concept of additivity, you can design your fact tables to support the kind of analysis your business needs. You can choose the appropriate level of granularity and ensure your data aggregations provide accurate and insightful results.
