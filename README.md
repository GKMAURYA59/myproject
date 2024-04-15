# myproject
I am uploading this simple project for begineers named as ONLINE BOOK STORE

create database Bookstore;
use bookstore;
CREATE TABLE books (
    book_id INT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(50),
    price DECIMAL(10, 2)
);

CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(30),
    email VARCHAR(50),
    address VARCHAR(100)
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id int,
	book_id int,
    quantity int,
    order_date date,
    foreign key (customer_id) references customers(customer_id),
    foreign key (book_id) references books(book_id)
   );
   
   CREATE TABLE payments (
    payment_id INT PRIMARY KEY,
    order_id INT,
    payment_date DATE,
    amount DECIMAL(10 , 2 ),
    FOREIGN KEY (order_id) REFERENCES orders (order_id)
);

insert into books (book_id, title, author,price) 
values (1,'Book 1', 'Author 1',10.99),
       (2,'Book 2','Author 2',12.99),
       (3, 'Book 3','Author 3',9.99),
       (4, 'Book 4','Author 4',15.99),
       (5, 'Book 5','Author 5',8.99);
       
insert into customers(customer_id, name,email,address) 
values (1,'customer 1','customer1@example.com','Address 1'),
(2,'customer 2','customer2@example.com','Address 2'),
(3,'customer 3','customer3@example.com','Address 3'),
(4,'customer 4','customer4@example.com','Address 4'),
(5,'customer 5','customer5@example.com','Address 5');

insert into orders (order_id, customer_id,book_id,quantity,order_date)
values (1,1,1,1,'2023-06-01'),
        (2,2,2,2,'2023-06-02'),
        (3,3,3,3,'2023-06-03'),
        (4,4,4,4,'2023-06-04'),
        (5,5,5,5,'2023-06-05');
        
insert into payments(payment_id,order_id,payment_date,amount)
values	(1,1,'2023-06-02',21.98),
		(2,2,'2023-06-03',9.99),
        (3,3,'2023-06-04',38.97),
        (4,4,'2023-06-05',31.98),
        (5,5,'2023-06-06',8.99);
        
