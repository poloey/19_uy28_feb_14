## about sql 

sql is declarative language. I mean what you want you can ask.    
some terminology of sql   

* DB - database
* DBA - database administrator
* DBMS - database management system
* RDBMS - relational database management system
* ddl - data definition language (creating table, altering table, primary key, foreign key)
* dml - (data manipulation language create read update delete - CRUD)

## creating a table - back-tic for escaping character

~~~php
create table cities (
  id int(11) auto_increment primary key,
  name varchar(30)
);

create table cities (
  id int(11) auto_increment,
  name varchar(30),
  primary key(id)
);

# with back-tic as escaping character    
create table cities (
  id serial,
  name varchar(30)
);
~~~
## table with foreign key

~~~php
create table people (
  id int(11) auto_increment primary key,
  first_name varchar(30) not null,
  last_name varchar(30) not null,
  email varchar(30),
  # structures should be like parent table
  city_id int(11),
  foreign key(city_id) references cities(id) 
);

create table people (
  id int(11) auto_increment primary key,
  first_name varchar(30) not null,
  last_name varchar(30) not null,
  email varchar(30),
  city_id bigint(20) unsigned,
  foreign key(city_id) references cities(id)
);
~~~

## knowing table structures 

~~~php
show columns from cities;
# or
describe cities;
~~~

## inserting data into database    

~~~php
insert into cities values(1, 'Feni');
# or
insert into cities (name) values('Feni');
# or
insert into cities set name='Feni';
~~~

## inserting multiple values in table
~~~php
insert into people(first_name, last_name, email, city_id) values
('Parvez', 'Ahmed', 'parvez@gmai.com', 1),
('Helal', 'Ahmed', 'helal@gmai.com', 1),
('Sarif', 'Ahmed', 'sarif@gmai.com', 2)
~~~

## some mysql functions 

* `count(value)`    
* `concat(value, value)`
* `concat_ws(separtor, value, value)`
* upper
* lower
* reverse

## join query 

~~~php
select * from people join cities where cities.id=people.city_id;
~~~

## altering table 

~~~php
# adding new column in table
alter table people add address varchar(255);
# adding new column with default value
alter table people add address varchar(255) default 'ssk road feni';
# for appearing after id
alter table people add address varchar(255) after id;
# for appearing in first 
alter table people add address varchar(255) first;
alter table people modify address varchar(255) default 'ssk road feni' first;
~~~

## truncating table 

~~~php
truncate people;
~~~

## how to export database 

~~~php
mysqldump -uroot -p people > filename.sql
~~~

## how to import to database 

~~~php
mysql -uroot -p people < filename.sql
~~~

## how to view select query horizontally 

~~~php
select * from people\G
~~~












