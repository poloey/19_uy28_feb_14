sql  is a declarative language. what you want you just ask him 

DB - database
DBA - database administrator
DBMS - database management system
RDBMS - relational database management system
ddl - data definition language (creating table, altering table, primary key, foreign key)
dml - (data manipulation language create read update delete - CRUD)

degrees 
================
id  name
1   physics 
2   chemistry


subjects
====================
id name                           degree_id
1 English                         2
2 Fundamental of chemistry        2
3 organic chemistry               2



cities
==================

create table cities (
  id int(11) auto_increment primary key,
  name varchar(30)
);
create table cities (
  id int(11) auto_increment,
  name varchar(30),
  primary key(id)
);

create table cities (
  id serial,
  name varchar(30)
);
people
===============

create table people (
  id int(11) auto_increment primary key,
  first_name varchar(30) not null,
  last_name varchar(30) not null,
  email varchar(30),
  city_id bigint(20) unsigned,
  foreign key(city_id) references cities(id)
);



// conditional table dropping 

drop table if exists cities;


insert into cities values(1, 'Feni');
insert into cities (name) values('Feni');
insert into cities set name='Feni';

insert into cities (name) values('Feni'),('Comilla'),('Barishal'),('Noakhali');

insert into people(first_name, last_name, email, city_id) values
('Parvez', 'Ahmed', 'parvez@gmai.com', 1),
('Helal', 'Ahmed', 'helal@gmai.com', 1),
('Sarif', 'Ahmed', 'sarif@gmai.com', 2),
('Shuvo', 'Ahmed', 'shuvo@gmai.com', 2),
('Ashraf', 'Ahmed', 'ashraf@gmai.com', 4),
('Akbar', 'Ahmed', 'akbar@gmai.com', 4),
('Sujon', 'Ahmed', 'sujon@gmai.com', 4),
('Mridul', 'Ahmed', 'mridul@gmai.com', 3),
('Tanha', 'Ahmed', 'tanha@gmai.com', 3)

select concat_ws('-----', first_name, last_name)  as name from people    

dry - do not repeat youself

filtering 
where 

# function
cout
concat 
cacat_ws 
upper
lower
reverse










