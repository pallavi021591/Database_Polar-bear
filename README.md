# Database_Polar-bear
CREATE DATABASE IF NOT EXISTS Polar_bear;
CREATE SCHEMA IF NOT EXISTS Polar_bear;
USE Polar_bear;

#String Data type
CHAR(5)
VARCHAR(5)
ENUM('M','F')

#Numeric Data Type
INTEGER - integer
FIXED POINT - decimal & numeric
FLOATING POINT - float, double

#Other Data type
DATE
DATETIME
TIMESTAMP

CREATE TABLE CUSTOMERS
(
  customer_id INT PRIMARY KEY,
  first_name VARCHAR(255),
  last_name VARCHAR(255),
  age INT,
  email_id VARCHAR(255),
  mobile_number INT,
  number_of_complaints INT DEFAULT 0
);

ALTER TABLE CUSTOMERS
ADD COLUMN gender ENUM('M','F') AFTER last_name;

DROP TABLE CUSTOMERS;

ALTER TABLE CUSTOMERS
ADD UNIQUE KEY(email_id);

ALTER TABLE CUSTOMERS
DROP INDEX(email_id);

INSERT INTO CUSTOMERS(first_name,last_name,gender,age,email_address,mobile_number,number_of_complaints)
VALUES
('Atul','Limje','M',36,'atullimje@360office.com',1234567878,0),
('Ishaan','Limje','M',2,'ishaanlimje@firstbaby.com',2739465849,1),
('Pallavi','Limje','F',32,'palllimje@coffice24.com',9870987656,3),
('Sudhakar','Lim','M',68,'sudhlim@homeoffice.com',1232345123,2),
('Sandhya','Lim','F',62,'sandhlim@homemaker.com',3456345457,2),
('Mohit','Limj','M',31,'mohitlimj@godrejoffice.com',2323434531,4),
('Geet','Limj','M',29,'geetlimj@tchemoffice.com',7654654876,3),
('Narendra','Nandanwar','M',63,'narennan@officeretire.com',7658765412,2),
('Sunita','Nandanwar','F',58,'sunitanan@homeminister.com',9089786541,0),
('Shivani','Kohadkar','F',26,'shivko@officesearch.com',7863862873,1),
('Akshay','Kohadkar','M',29,'akshayko@germanoffice.com',76567875412,4),
('Harish','Nandan','M',60,'harishnandan@officeretirement.com',8787824562,4),
('Pranita','Nandan','F',56,'pranitanandan@makerhome.com',8909876543,3),
('Tejas','Nandan','M',23,'tejunandan@searchindia.com',66888777775,0),
('Anuja','Dekate','F',26,'anu@fitttraining.com',1258765412,5),
('Dheeraj','Dekate','M',35,'dheeraj@propertydealer.com',987765412,6),
('Anay','Dekate','M',2,'anay@setji.com',9876444112,1);


CREATE TABLE SALES
(
  purchase_number INT AUTO INCREMENT PRIMARY KEY,
  date_of_purchase INT,
  customer_id INT,
  item_code VARCHAR(10)
);

INSERT INTO SALES(date_of_purchase,customer_id,item_code)
VALUES
('2022-05-01','1','001'),
('2023-04-11','12','002'),
('2023-01-30','17','001'),
('2022-09-27','16','004'),
('2022-11-17','2','005'),
('2024-04-14','3','009'),
('2023-05-21','1','020'),
('2023-02-06','15','023'),
('2022-08-02','14','003'),
('2023-04-27','13','001'),
('2023-05-01','8','021'),
('2022-04-29','10','021'),
('2022-05-05','11','012'),
('2024-02-22','12','019'),
('2023-07-17','9','017'),
('2022-04-28','7','019'),
('2022-07-25','6','017'),
('2023-03-03','6','012'),
('2022-12-12','6','023'),
('2024-11-11','5','001'),
('2022-10-10','15','024'),
('2023-11-07','16','001'),
('2022-09-09','17','001'),
('2023-02-20','4','008'),
('2024-02-20','9','004'),
('2022-10-10','8','001'),
('2022-04-30','10','001'),
('2024-03-31','17','023'),
('2023-05-11','12','001'),
('2022-04-21','12','002'),
('2024-01-03','1','001'),
('2023-09-04','11','004'),
('2022-11-17','12','005'),
('2024-04-14','3','009'),
('2023-05-08','1','020'),
('2023-02-28','17','023'),
('2022-08-29','15','003'),
('2023-04-27','12','001'),
('2023-05-05','8','021'),
('2024-04-29','10','002'),
('2022-05-15','11','001'),
('2024-02-22','12','019'),
('2023-07-17','9','017'),
('2022-04-23','8','019'),
('2022-07-25','6','017'),
('2023-03-28','8','021'),
('2022-12-22','6','003'),
('2024-11-01','5','001'),
('2022-10-01','15','001'),
('2023-11-02','16','001'),
('2022-09-09','17','022'),
('2023-02-04','8','008'),
('2024-02-09','9','008'),
('2022-10-10','8','001'),
('2022-04-30','10','022'),
('2024-03-31','17','023'),



CREATE TABLE ITEMS
(
  item_code VARCHAR(255) PRIMARY KEY,
  item VARCHAR(255)
  unit_price NUMERIC(10,2)
  flavour_id VARCHAR(255)
);

INSERT INTO ITEMS(item_code,item,unit_price,flavour_id)
VALUES
('001','Choco Block',165,'17'),
('002','Excess Chocolate',195,'2'),
('003','Rocky Roads',175,'11'),
('004','Choco Brownie Fudge',185,'1'),
('005','Cookie Monster',185,'4'),
('006','Chocolava Fudge',170,'18'),
('007','Brownie Fudge',170,'10'),
('008','Red Velvet Choco Sin',185,'16'),
('009','Chocozilla',195,'14'),
('010','MY DBC',195,'15'),
('011','Death By Chocolate',165,'7'),
('012','DBC Duet',295,'12'),
('013','Mega DBC',495,'13'),
('014','MY DBC',195,'15'),
('015','Super Bowl',575,'5'),
('016','Seven Wonders',295,'16'),
('017','Family Pizza',435,'8'),
('018','Gelly belly',95,'9'),
('019','Cookie Man',95,'10'),
('020','Chocolate Man',95,'11'),
('021','Hot chocolate Fudge Junior','79','7'),
('022','Hot chocolate Fudge Medium','135','6'),
('023','Hot chocolate Fudge Jumbo','175','3');


CREATE TABLE FLAVOURS
(
  flavour_id VARCHAR(255) AUTO INCREAMENT PRIMARY KEY,
  flavour_name VARCHAR(255) NOT NULL
)

INSERT INTO FLAVOURS(flavour_name)
VALUES
('Chocolate'),
('Vanilla'),
('Strawberry'),
('Mint Chocolate Chip'),
('Choco Almond'),
('Cookies n Cream'),
('Buttercotch'),
('Mangoista'),
('Guava'),
('Pinepapaya'),
('Coffee Almond'),
('Fruit n Nuts'),
('Badam Rangeela'),
('Kiwi paste'),
('Black n White'),
('Ice Chilly'),
('German Chocolate'),
('Ice-cream Brownie'),
('Honey n Cherry'),
('Rajbhog'),
('Chappanbhog');

ALTER TABLE FLAVOURS
MODIFY(flavour_name) NULL;

ALTER TABLE FLAVOURS
CHANGE COLUMN flavour_name. flavour_name NOT NULL;
