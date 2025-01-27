use ap;

-- 1. Basic SELECT Statement: Write a query to fetch all columns from the vendors table.
	-- Output Columns: All columns from the vendors table.
	-- Order By: vendor_id
SELECT * 
FROM vendors 
ORDER BY vendor_id;

-- 2. WHERE Clause: Write a query to fetch the vendor_name, vendor_phone, and vendor_city 
-- from the vendors table for vendors located in the state of 'CA'.
	-- Output Columns: vendor_name, vendor_phone, vendor_city.
    -- Order By: vendor_name
SELECT vendor_name, vendor_phone, vendor_city
FROM vendors
WHERE vendor_state = 'CA'
ORDER BY vendor_name;

-- 3. Sorting Results: Write a query to fetch the invoice_id, invoice_total, and invoice_date 
-- from the invoices table, sorted by invoice_total in descending order.
	-- Output Columns: invoice_id, invoice_total, invoice_date.
SELECT invoice_id, invoice_total, invoice_date
FROM invoices
ORDER BY invoice_total DESC;

-- 4. Limiting Results: Write a query to fetch the invoices with the  3rd to 9th lowest 
-- invoice_total from the invoices table.
	-- Output Columns: invoice_id, invoice_total.
	-- Order By: invoice_total
SELECT invoice_id, invoice_total
FROM invoices
ORDER BY invoice_total
LIMIT 7 OFFSET 2; -- OFFSET 2 skips the first two rows and LIMIT 7 selects the next 7 rows

-- 5. Using Arithmetic: Write a query to fetch the invoice_id, invoice_total, and the remaining 
-- balance (calculated as invoice_total - payment_total) for all invoices in the invoices table.
	-- Output Columns: invoice_id, invoice_total, Remaining Balance
	-- Order By: invoice_id
SELECT invoice_id, invoice_total, (invoice_total - payment_total) AS Remaining_Balance
FROM invoices
ORDER BY invoice_id;
-- 'invoice_total - payment_total' calculates the remaining balance 


-- 6. Inner Join: Write a query to fetch the invoice_id, invoice_total, vendor_name, and vendor_phone for 
-- all invoices. Use an inner join between the invoices and vendors tables.
	-- Output Columns: invoice_id, invoice_total, vendor_name, vendor_phone.
	-- Order By: Invoice_id
SELECT 
    invoices.invoice_id, 
    invoices.invoice_total, 
    vendors.vendor_name, 
    vendors.vendor_phone
FROM invoices
INNER JOIN vendors 
    ON invoices.vendor_id = vendors.vendor_id
ORDER BY invoices.invoice_id;

-- 7. Outer Join: Write a query to fetch all vendor_name values along with the invoice_id. 
-- Include vendors who do not have any invoices. 
	-- Output Columns: vendor_name, invoice_id
	-- Order By: vendor_name
 SELECT 
    vendors.vendor_name, 
    invoices.invoice_id
FROM vendors
LEFT OUTER JOIN invoices -- Ensures all vendors are included, even if they 
								-- don't have matching invoices.
    ON vendors.vendor_id = invoices.vendor_id
ORDER BY vendors.vendor_name;


-- 8. Outer Join 2: Using the ex database; write a query to fetch all department_name 
-- values along with the employees last_name for each department. Include employees 
-- that do not have a matching department.
	-- Output Columns: department_name, employee_last_name.
	-- Order By: department_id
USE ex;
SELECT 
    departments.department_name, 
    employees.last_name AS employee_last_name
FROM employees
RIGHT OUTER JOIN departments 
    ON employees.department_number = departments.department_number 
    -- didn't find department_id so i am using department_number
ORDER BY departments.department_number;

DESCRIBE employees;
DESCRIBE departments;


-- 9. Using CONCAT Write a query to fetch a single column combining the first_name 
-- and last_name (formatted as "FirstName LastName") along with their vendor_name. 
-- Use the vendor_contacts and vendors tables.
	-- Output Columns: Combined Contact Name, vendor_name.
	-- Order By: Combined Contact Name
USE ap;
SELECT 
    CONCAT(vendor_contacts.first_name, ' ', 
    vendor_contacts.last_name) AS "Combined Contact Name", 
    vendors.vendor_name
FROM vendor_contacts
INNER JOIN vendors 
    ON vendor_contacts.vendor_id = vendors.vendor_id
ORDER BY "Combined Contact Name";

-- 10. Union: using the ex database; Write a query to fetch all unique first_name values 
-- from both the employees and sales_reps tables.
	-- Output Columns: first_name.
	-- Order By: first_name
USE ex;

SELECT first_name
FROM employees
UNION
SELECT rep_first_name AS first_name -- Retrieves the rep_first_name from the sales_reps
					--  table and renames it as first_name to match the output format.
FROM sales_reps
ORDER BY first_name;

describe employees;
describe sales_reps;


-- 11. Complex Query with Multiple Joins: Write a query to fetch the invoice_id, invoice_total,
-- vendor_name, and terms_description for all invoices. Use appropriate joins between the invoices, vendors, and terms tables.
	-- Output Columns: invoice_id, invoice_total, vendor_name, terms_description.
	-- Order By: invoice_id
use ap;
SELECT 
    invoices.invoice_id, 
    invoices.invoice_total, 
    vendors.vendor_name, 
    terms.terms_description
FROM invoices
INNER JOIN vendors 
    ON invoices.vendor_id = vendors.vendor_id
INNER JOIN terms 
    ON invoices.terms_id = terms.terms_id
ORDER BY invoices.invoice_id;






   






