
select sum(quantity * list_price * (1-discount))
       as 'Total Sales '
from sales.order_items;



select count(*) as 'Total Order'
from sales.orders;

select avg(OrderTotal) as 'Average Order Value'
from (
    select order_id,
     sum(quantity * list_price * (1-discount)) as OrderTotal
    from sales.order_items
    group by order_id
)o ;



select count(*) as 'Total Customers'
from sales.customers;


select sum(quantity) as 'Total Quantity'
from sales.order_items;



select year(o.order_date) as Year,month(o.order_date) as Month,
       sum(oi.quantity * oi.list_price * (1-oi.discount)) as Sales
from sales.orders o
join sales.order_items oi
    on o.order_id = oi.order_id
group by year(o.order_date),
         month(o.order_date)
order by Year, Month;



select top 10 p.product_name,
       sum(oi.quantity * oi.list_price * (1-oi.discount))as Sales
from production.products p
join sales.order_items oi
on p.product_id = oi.product_id
group by p.product_name
order by Sales desc;



select top 10 p.product_name,sum(oi.quantity) as 'Total Quantity'
from production.products p
join sales.order_items oi
on p.product_id = oi.product_id
group by p.product_name
order by 'Total Quantity' desc ;



select s.store_name, 
       sum(oi.quantity * oi.list_price * (1-oi.discount))as Sales 
from sales.stores s
join sales.orders o
on s.store_id = o.store_id
join sales.order_items oi
on o.order_id = oi.order_id
group by s.store_name
order by sales desc;



select s.first_name+' '+s.last_name as 'Full Name ',
       sum(oi.quantity * oi.list_price * (1-oi.discount))as Sales 
from sales.staffs s
join sales.orders o
on s.staff_id = o.staff_id
join sales.order_items oi
on o.order_id = oi.order_id
group by s.first_name,s.last_name
order by sales desc;


select category_name , 
       sum(oi.quantity * oi.list_price * (1-oi.discount))as Sales 
from production.categories c
join production.products p
on c.category_id = p.category_id
join sales.order_items oi
on p.product_id = oi.product_id 
group by category_name
order by sales desc;


select top 10 p.product_name ,
      sum(s.quantity) as 'stock quantity'
from production.products p
join production.stocks s
on p.product_id = s.product_id
group by p.product_name 
order by 'stock quantity'asc;
