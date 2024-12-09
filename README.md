# Northwind OData Queries

This is the documentation of the postman collection of this project. Below is the solution to the odata exercises presented in the lessons of the SAP bootcamp. 

## Base URL
```
https://services.odata.org/northwind/northwind.svc/
```

## Query Examples

### 1. Orders with Customer Details
**Endpoint:** `Orders`
**Query Parameters:**
- `$format=json`: Return results in JSON format
- `$expand=Customer`: Include related customer information

**Full Query:**
```
/Orders?$format=json&$expand=Customer
```

**Purpose:** Retrieve all orders along with their associated customer details.

### 2. Employees Reporting to Manager 2
**Endpoint:** `Employees`
**Query Parameters:**
- `$format=json`: Return results in JSON format
- `$filter=ReportsTo eq 2`: Filter employees who report to manager with ID 2

**Full Query:**
```
/Employees?$format=json&$filter=ReportsTo eq 2
```

**Purpose:** List all employees who report to a specific manager (in this case, manager ID 2).

### 3. Products in Stock
**Endpoint:** `Products`
**Query Parameters:**
- `$format=json`: Return results in JSON format
- `$filter=UnitsInStock gt 0`: Filter products with stock greater than 0

**Full Query:**
```
/Products?$format=json&$filter=UnitsInStock gt 0
```

**Purpose:** Retrieve all products that currently have inventory in stock.

### 4. Products with No Stock
**Endpoint:** `Products`
**Query Parameters:**
- `$format=json`: Return results in JSON format
- `$filter=UnitsInStock eq 0`: Filter products with zero stock

**Full Query:**
```
/Products?$format=json&$filter=UnitsInStock eq 0
```

**Purpose:** List products that are currently out of stock.

### 5. Most Expensive Products
**Endpoint:** `Products`
**Query Parameters:**
- `$format=json`: Return results in JSON format
- `$orderby=UnitPrice desc`: Sort by unit price in descending order
- `$top=5`: Limit to top 5 results

**Full Query:**
```
/Products?$format=json&$orderby=UnitPrice desc&$top=5
```

**Purpose:** Retrieve the 5 most expensive products in the catalog.

### 6. Orders Shipped to Germany
**Endpoint:** `Orders`
**Query Parameters:**
- `$filter=ShipCountry eq 'Germany'`: Filter orders shipped to Germany
- `$format=json`: Return results in JSON format

**Full Query:**
```
/Orders?$filter=ShipCountry eq 'Germany'&$format=json
```

**Purpose:** Find all orders that were shipped to Germany.

### 7. Beverages: Names and Prices
**Endpoint:** `Products`
**Query Parameters:**
- `$filter=CategoryID eq 1`: Filter for Beverages category
- `$select=ProductName,UnitPrice`: Select only product name and price
- `$format=json`: Return results in JSON format
- `$expand=Category`: Include category details

**Full Query:**
```
/Products?$filter=CategoryID eq 1&$select=ProductName,UnitPrice&$format=json&$expand=Category
```

**Purpose:** Obtain names and prices of all products in the Beverages category.

## OData Query Parameter Reference
- `$format`: Specify the response format
- `$expand`: Include related entities
- `$filter`: Apply filtering conditions
- `$select`: Choose specific fields
- `$orderby`: Sort results
- `$top`: Limit number of results

## Notes
- All queries use the Northwind sample database
- Queries are case-sensitive and follow OData v2 specification
- Results can be further customized using additional OData query parameters
