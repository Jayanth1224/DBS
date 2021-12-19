# DBS
DB


create database DBS;
use DBS;
create table Customer_table(customer_id int primary key, customer_name varchar(255),user_id varchar(255),password varchar(255));
create table Stocks(stock_id int primary key, stock_name varchar(255), current_price int(255));
show tables;

Create Table Stock_book_order
(
Order_id Int Primary Key,
order_type varchar(255),
price int, quantity int,
order_date date,
Foreign Key(stock_id) REFERENCES Stocks(stock_id),
Foreign Key(customer_id) REFERENCES Customer_table(customer_id)
);
create table Admin
(
foreign key(order_id) references Stock_book_order(order_id),
stock_name varchar(255),
order_status varchar(255) default 'Placed'
);
