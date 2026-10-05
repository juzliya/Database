CREATE TABLE Airline\_info (

&#x20;   airline\_id INT PRIMARY KEY,

&#x20;   airline\_code VARCHAR(30) NOT NULL,

&#x20;   airline\_name VARCHAR(50) NOT NULL,

&#x20;   airline\_country VARCHAR(50) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL,

&#x20;   info VARCHAR(50) NOT NULL

);





CREATE TABLE Airport (

&#x20;   airport\_id INT PRIMARY KEY,

&#x20;   airport\_name VARCHAR(50) NOT NULL,

&#x20;   country VARCHAR(50) NOT NULL,

&#x20;   state VARCHAR(50) NOT NULL,

&#x20;   city VARCHAR(50) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL

);





CREATE TABLE Passengers (

&#x20;   passenger\_id INT PRIMARY KEY,

&#x20;   first\_name VARCHAR(50) NOT NULL,

&#x20;   last\_name VARCHAR(50) NOT NULL,

&#x20;   date\_of\_birth DATE NOT NULL,

&#x20;   gender VARCHAR(50) NOT NULL,

&#x20;   country\_of\_citizenship VARCHAR(50) NOT NULL,

&#x20;   country\_of\_residence VARCHAR(50) NOT NULL,

&#x20;   passport\_number VARCHAR(20) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL

);





CREATE TABLE Flights (

&#x20;   flight\_id INT PRIMARY KEY,

&#x20;   sch\_departure\_time TIMESTAMP NOT NULL,

&#x20;   sch\_arrival\_time TIMESTAMP NOT NULL,

&#x20;   departing\_airport\_id INT NOT NULL,

&#x20;   arriving\_airport\_id INT NOT NULL,

&#x20;   departing\_gate VARCHAR(50) NOT NULL,

&#x20;   arriving\_gate VARCHAR(50) NOT NULL,

&#x20;   airline\_id INT NOT NULL,

&#x20;   act\_departure\_time TIMESTAMP NOT NULL,

&#x20;   act\_arrival\_time TIMESTAMP NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL

);





CREATE TABLE Booking (

&#x20;   booking\_id INT PRIMARY KEY,

&#x20;   flight\_id INT NOT NULL,

&#x20;   passenger\_id INT NOT NULL,

&#x20;   booking\_platform VARCHAR(50) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL,

&#x20;   status VARCHAR(50) NOT NULL,

&#x20;   price DECIMAL(7, 2) NOT NULL

);



\-- 6. Таблица Baggage\_check

CREATE TABLE Baggage\_check (

&#x20;   baggage\_check\_id INT PRIMARY KEY,

&#x20;   check\_result VARCHAR(50) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL,

&#x20;   booking\_id INT NOT NULL,

&#x20;   passenger\_id INT NOT NULL

);





CREATE TABLE Baggage (

&#x20;   baggage\_id INT PRIMARY KEY,

&#x20;   weight\_in\_kg DECIMAL(4, 2) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL,

&#x20;   booking\_id INT NOT NULL

);





CREATE TABLE Boarding\_pass (

&#x20;   boarding\_pass\_id INT PRIMARY KEY,

&#x20;   booking\_id INT NOT NULL,

&#x20;   seat VARCHAR(50) NOT NULL,

&#x20;   boarding\_time TIMESTAMP NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL

);





CREATE TABLE Booking\_flight (

&#x20;   booking\_flight\_id INT PRIMARY KEY,

&#x20;   booking\_id INT NOT NULL,

&#x20;   flight\_id INT NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL

);





CREATE TABLE Security\_check (

&#x20;   security\_check\_id INT PRIMARY KEY,

&#x20;   check\_result VARCHAR(20) NOT NULL,

&#x20;   created\_at TIMESTAMP NOT NULL,

&#x20;   updated\_at TIMESTAMP NOT NULL,

&#x20;   passenger\_id INT NOT NULL

);









INSERT INTO Airline\_info (airline\_id, airline\_code, airline\_name, airline\_country, created\_at, updated\_at, info) VALUES

(1, 'KC', 'Air Astana', 'Kazakhstan', '2024-03-12 11:24:00', '2024-03-12 11:24:00', 'National carrier'),

(2, 'DV', 'SCAT Airlines', 'Kazakhstan', '2024-03-15 14:05:12', '2024-03-15 14:05:12', 'Regional carrier'),

(3, 'TK', 'Turkish Airlines', 'Turkey', '2024-04-01 09:40:30', '2024-04-01 09:40:30', 'International partner'),

(4, 'FZ', 'Flydubai', 'UAE', '2024-05-10 16:15:00', '2024-05-10 16:15:00', 'Low-cost carrier'),

(5, 'QR', 'Qatar Airways', 'Qatar', '2024-06-22 10:00:45', '2024-06-22 10:00:45', 'Global airline');



INSERT INTO Airport (airport\_id, airport\_name, country, state, city, created\_at, updated\_at) VALUES

(1, 'Almaty International Airport', 'Kazakhstan', 'Almaty Region', 'Almaty', '2024-01-15 08:30:00', '2024-01-15 08:30:00'),

(2, 'Nursultan Nazarbayev International Airport', 'Kazakhstan', 'Akmola Region', 'Astana', '2024-01-15 08:45:10', '2024-01-15 08:45:10'),

(3, 'Dubai International Airport', 'UAE', 'Dubai', 'Dubai', '2024-02-03 12:10:00', '2024-02-03 12:10:00'),

(4, 'Istanbul Airport', 'Turkey', 'Istanbul', 'Istanbul', '2024-02-10 15:20:00', '2024-02-10 15:20:00'),

(5, 'Hamad International Airport', 'Qatar', 'Doha', 'Doha', '2024-02-18 11:05:40', '2024-02-18 11:05:40');



INSERT INTO Passengers (passenger\_id, first\_name, last\_name, date\_of\_birth, gender, country\_of\_citizenship, country\_of\_residence, passport\_number, created\_at, updated\_at) VALUES

(1, 'Jamilya', 'Zholdas', '2002-05-14', 'Female', 'Kazakhstan', 'Kazakhstan', 'N1048291', '2026-08-10 14:22:05', '2026-08-10 14:22:05'),

(2, 'Ayazhan', 'Kydyr', '2001-11-20', 'Female', 'Kazakhstan', 'Kazakhstan', 'N0847204', '2026-08-12 11:04:30', '2026-08-12 11:04:30'),

(3, 'Ivan', 'Ivanov', '1995-03-10', 'Male', 'Kazakhstan', 'Kazakhstan', 'N9381047', '2026-08-15 16:40:12', '2026-08-15 16:40:12'),

(4, 'Petr', 'Petrov', '1988-07-25', 'Male', 'Kazakhstan', 'Kazakhstan', 'N4729103', '2026-08-18 09:15:00', '2026-08-18 09:15:00'),

(5, 'Anna', 'Sidorova', '1999-12-05', 'Female', 'Kazakhstan', 'Kazakhstan', 'N5839201', '2026-08-20 18:30:45', '2026-08-20 18:30:45');



INSERT INTO Flights (flight\_id, sch\_departure\_time, sch\_arrival\_time, departing\_airport\_id, arriving\_airport\_id, departing\_gate, arriving\_gate, airline\_id, act\_departure\_time, act\_arrival\_time, created\_at, updated\_at) VALUES

(1, '2026-09-20 08:00:00', '2026-09-20 09:40:00', 1, 2, 'A1', 'B2', 1, '2026-09-20 08:07:12', '2026-09-20 09:43:00', '2026-07-01 10:15:00', '2026-09-20 09:43:00'),

(2, '2026-09-20 12:00:00', '2026-09-20 16:30:00', 1, 3, 'A3', 'C1', 4, '2026-09-20 12:02:40', '2026-09-20 16:22:15', '2026-07-01 10:15:00', '2026-09-20 16:22:15'),

(3, '2026-09-21 06:00:00', '2026-09-21 10:15:00', 1, 4, 'A2', 'D4', 3, '2026-09-21 06:14:05', '2026-09-21 10:23:50', '2026-07-05 11:00:00', '2026-09-21 10:23:50'),

(4, '2026-09-21 15:00:00', '2026-09-21 16:40:00', 2, 1, 'B1', 'A5', 2, '2026-09-21 15:00:00', '2026-09-21 16:36:10', '2026-07-05 11:00:00', '2026-09-21 16:36:10'),

(5, '2026-09-22 01:00:00', '2026-09-22 05:30:00', 1, 5, 'A4', 'E2', 5, '2026-09-22 01:03:22', '2026-09-22 05:27:00', '2026-07-10 14:20:00', '2026-09-22 05:27:00');



INSERT INTO Booking (booking\_id, flight\_id, passenger\_id, booking\_platform, created\_at, updated\_at, status, price) VALUES

(101, 1, 1, 'Kaspi Travel', '2026-09-01 10:14:20', '2026-09-01 10:15:02', 'Confirmed', 120.00),

(102, 2, 2, 'AirAstana App', '2026-09-02 11:32:10', '2026-09-02 11:34:40', 'Confirmed', 350.00),

(103, 3, 3, 'Aviata', '2026-09-03 14:05:50', '2026-09-03 14:08:15', 'Confirmed', 420.00),

(104, 4, 4, 'Website', '2026-09-04 16:44:03', '2026-09-04 16:45:00', 'Confirmed', 115.00),

(105, 5, 5, 'Trip.com', '2026-09-05 18:21:11', '2026-09-05 18:22:00', 'Confirmed', 500.00);



INSERT INTO Baggage\_check (baggage\_check\_id, check\_result, created\_at, updated\_at, booking\_id, passenger\_id) VALUES

(1, 'Passed', '2026-09-20 06:34:12', '2026-09-20 06:36:00', 101, 1),

(2, 'Passed', '2026-09-20 10:18:45', '2026-09-20 10:21:10', 102, 2),

(3, 'Passed', '2026-09-21 04:22:00', '2026-09-21 04:25:30', 103, 3),

(4, 'Passed', '2026-09-21 13:12:50', '2026-09-21 13:15:00', 104, 4),

(5, 'Passed', '2026-09-21 23:04:15', '2026-09-21 23:07:40', 105, 5);



INSERT INTO Baggage (baggage\_id, weight\_in\_kg, created\_at, updated\_at, booking\_id) VALUES

(1, 18.50, '2026-09-20 06:34:12', '2026-09-20 06:34:12', 101),

(2, 22.10, '2026-09-20 10:18:45', '2026-09-20 10:18:45', 102),

(3, 15.00, '2026-09-21 04:22:00', '2026-09-21 04:22:00', 103),

(4, 19.80, '2026-09-21 13:12:50', '2026-09-21 13:12:50', 104),

(5, 23.00, '2026-09-21 23:04:15', '2026-09-21 23:04:15', 105);



INSERT INTO Boarding\_pass (boarding\_pass\_id, booking\_id, seat, boarding\_time, created\_at, updated\_at) VALUES

(1, 101, '12A', '2026-09-20 07:20:00', '2026-09-20 06:34:12', '2026-09-20 06:34:12'),

(2, 102, '15F', '2026-09-20 11:20:00', '2026-09-20 10:18:45', '2026-09-20 10:18:45'),

(3, 103, '04C', '2026-09-21 05:20:00', '2026-09-21 04:22:00', '2026-09-21 04:22:00'),

(4, 104, '10B', '2026-09-21 14:20:00', '2026-09-21 13:12:50', '2026-09-21 13:12:50'),

(5, 105, '02A', '2026-09-22 00:20:00', '2026-09-21 23:04:15', '2026-09-21 23:04:15');



INSERT INTO Booking\_flight (booking\_flight\_id, booking\_id, flight\_id, created\_at, updated\_at) VALUES

(1, 101, 1, '2026-09-01 10:15:02', '2026-09-01 10:15:02'),

(2, 102, 2, '2026-09-02 11:34:40', '2026-09-02 11:34:40'),

(3, 103, 3, '2026-09-03 14:08:15', '2026-09-03 14:08:15'),

(4, 104, 4, '2026-09-04 16:45:00', '2026-09-04 16:45:00'),

(5, 105, 5, '2026-09-05 18:22:00', '2026-09-05 18:22:00');



INSERT INTO Security\_check (security\_check\_id, check\_result, created\_at, updated\_at, passenger\_id) VALUES

(1, 'Passed', '2026-09-20 06:48:10', '2026-09-20 06:48:10', 1),

(2, 'Passed', '2026-09-20 10:35:22', '2026-09-20 10:35:22', 2),

(3, 'Passed', '2026-09-21 04:41:05', '2026-09-21 04:41:05', 3),

(4, 'Passed', '2026-09-21 13:30:15', '2026-09-21 13:30:15', 4),

(5, 'Passed', '2026-09-21 23:22:40', '2026-09-21 23:22:40', 5);



SELECT \* FROM Airline\_info;

SELECT \* FROM Airport;

SELECT \* FROM Passengers;

SELECT \* FROM Flights;

SELECT \* FROM Booking;

SELECT \* FROM Baggage\_check;

SELECT \* FROM Baggage;

SELECT \* FROM Boarding\_pass;

SELECT \* FROM Booking\_flight;

SELECT \* FROM Security\_check;



ALTER TABLE Airline\_info RENAME TO Airline;

ALTER TABLE Booking RENAME COLUMN price TO ticket\_price;

ALTER TABLE Flights MODIFY departing\_gate TEXT;

ALTER TABLE Airline DROP COLUMN info;

ALTER TABLE Flights 

&#x20;   ADD CONSTRAINT fk\_flights\_airline 

&#x20;   FOREIGN KEY (airline\_id) REFERENCES Airline(airline\_id);





