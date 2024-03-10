1. 
   Product: This entity represents a product sold by the e-commerce store. It has attributes such as id, name, desc, SKU, category_id, and price.
   
   Product_Category: This entity represents a category that products can be assigned to. It has attributes such as id, name, desc, created_at, modified_at, and deleted_at.

   The relationship between these two entities is one-to-many. A product can belong to one category (represented by the category_id foreign key in the Product table), but a category can have many products. This is a common way to organize products in an e-commerce system. It allows stores to group products together based on shared characteristics, such as type, color, or brand.
   This makes it easier for customers to find the products they are looking for.


2.
       In  5 ways we can ensure that each product in the "Product" table has a valid category assigned to it:
       
   1.  Data Validation on Insert:
  Database Constraints: You can set up a foreign key constraint on the category_id column in the Product table. This constraint would reference the primary key (id) of the Product_Category table. When adding a new product, the database would check if the referenced category ID exists. If it doesn't, the insert operation would fail, preventing an invalid assignment.
  2.  Data Validation on User Interface:
   Dropdown Menu: When creating a new product in the user interface (admin panel etc.), you can display a dropdown menu populated with valid categories from the Product_Category table. This restricts users from entering invalid category IDs.
  3.  Default Category:
   Default Value: You could set a default value for the category_id column in the Product table. This default value could be a category like "Uncategorized" but it's important to have a designated category for such cases. This approach should be combined with other methods to encourage proper categorization.
  4.  Data Verification and Correction:
   Validation Script: You can implement a script that periodically checks for products with invalid category IDs. This script could identify and flag such products or even attempt to update them with a valid category based on pre-defined rules.
  5.  Data Integrity Checks:
   Regular Checks: Regularly run queries or reports that identify products with missing or invalid category assignments. This allows you to take manual actions to correct the data.