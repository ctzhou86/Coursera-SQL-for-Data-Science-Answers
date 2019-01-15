1.Pull a list of customer ids with the customer’s full name, and address, along with combining their city and country together. Be sure to make a space in between these two and make it UPPER CASE.

select CustomerId,FirstName,LastName, Address,
upper(City || ' ' || Country) as CityCountry 
from Customers
where CustomerId=16

2.Create a new employee user id by combining the first 4 letter of the employee’s first name with the first 2 letters of the employee’s last name. Make the new field lower case and pull each individual step to show your work.

select FirstName,LastName,
lower(substr(FirstName,1,4) || substr(LastName,1,2)) as NewId
from Employees
where FirstName like "Robert" and LastName like "King";

3.Show a list of employees who have worked for the company for 15 or more years using the current date function. Sort by lastname ascending.

select LastName,HireDate,strftime('%Y',HireDate) as year,
2019-strftime('%Y',HireDate) as HireYear
from Employees
order by LastName asc

4. Profiling the Customers table, answer the following question.

select *
from Customers

5. Find the cities with the most customers and rank in descending order.

select City,CustomerId,count(CustomerId) as Count
from Customers
group by City
having Count=2

6. Create a new customer invoice id by combining a customer’s invoice id with their first and last name while ordering your query in the following order: firstname, lastname, and invoiceID.

select a.FirstName,a.LastName,a.InvoiceId,
a.FirstName || a.LastName || a.InvoiceId as NewInvoiceId
from
(select i.InvoiceId,c.FirstName,c.LastName
from Invoices as i
left join Customers as c
on i.CustomerId=c.CustomerId) as a
where a.FirstName like "Astrid"
