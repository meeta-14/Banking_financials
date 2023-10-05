
create database start;

use start;

create table performance_ratios(bank_id int primary key,bank_name char(50), casa float, roe float,roa float,nim float, roce float);

insert into performance_ratios values
    (1,'HDFC BANK',44.37,15.89,1.81,3.67,3.1),
    (2,'BANK OF BARODA',39.47,14.36,0.96,2.83,1.91),
    (3,'SBI',42.66,16.8,0.93,2.7,1.74),
    (4,'ICICI BANK LTD',45.83,16.13,2.01,3.92,3.27),
    (5,'KOTAK MAHINDRA',52.82,13.17,2.23,4.39,3.15),
    (6,'AXIS ',47.15,7.63,0.72,3.26,1.57),
    (7,'PUNJAB NATIONAL BANK',41.99,2.74,0.17,2.74,1.57),
    (8,'CANARA',31.08,16.03,0.78,2.33,2.11),
    (9,'IDBI BANK LTD',53.01,9.82,1.1,3.45,2.78),
    (10,'INDUSIND BANK LTD',40.14,13.6,1.61,3.84,3.26);

create table valuation_ratios(bank_id int, price_to_earnings float, price_to_book float, eps float);

insert into valuation_ratios values
    (1,19.48,3.1,82.64),
    (2,5.86,0.83,28.82),
    (3,8.4,1.41,62.35),
    (4,17.95,2.9,48.86),
    (5,23.12,3.08,74.96),
    (6,24.39,2.04,35.2),
    (7,13.22,1.15,1.94),
    (8,4.58,6.5,62.04),
    (9,13.04,1.27,3.45),
    (10,11.12,1.52,96.01);
    
 alter table valuation_ratios
 add foreign key (bank_id)
 references performance_ratios(bank_id);
    
create table  npa_in_percentage(bank_id int, gross float, net float);

 insert into  npa_in_percentage values
    (1,1.17,0.3),
    (2,3.51,0.78),
    (3,2.76,0.71),
    (4,2.76,0.48),
    (5,1.75,0.43),
    (6,1.96,0.41),
    (7,6.8,1.95),
    (8,5.15,1.57),
    (9,5.05,0.44),
    (10,1.94,0.58);

alter table npa_in_percentage
add foreign key (bank_id)
references performance_ratios(bank_id);


#Dashboard of banking sector performance comparison of top 10 banks in India:

https://acrobat.adobe.com/id/urn:aaid:sc:AP:b30b55b1-a2c0-4871-b0ef-4edffcbdcaa8


