
**Project**-:  Monitoring and Control of HVAC System in Pharmaceutical Cleanroom

**Background**:
A pharmaceutical company runs a cleanroom facility where medicines and other highly sensitive items are produced. The cleanroom's HVAC system is essential for maintaining the necessary levels of humidity, temperature, and air quality. However, the company pays high energy costs as a result of the HVAC system's inefficient operation, and the inconsistent environmental conditions are endangering the product quality.

**Goals**:

Real-time monitoring of HVAC system performance to ensure consistent environmental conditions in the cleanroom.
Real-time control of the HVAC system to maintain the required temperature, humidity, and air quality levels.

Equipment table - stores information about the HVAC equipment installed in the cleanroom, including the equipment name, make, model, installation date, and maintenance history.
Performance table - stores real-time data about the HVAC system's performance, including temperature, humidity, airflow, and air quality measurements.
Setpoints table - stores the setpoints for the temperature, humidity, and air quality levels in the cleanroom.
Control table - stores real-time control signals for the HVAC system, including the control mode, fan speed, and temperature setpoint.

**SQL Queries**

-->Create Equipment Table
create table Equipment(
Equipment_ID serial primary key,
Equipment_Name varchar(20),
Make varchar(20),
Model Varchar(20),
Installation_Date date,
Maintenance_History varchar(50)
)

select*from Equipment
drop table Equipment
insert into Equipment(Equipment_ID,Equipment_Name,Make,Model,Installation_Date,Maintenance_History)
values
(1,'HVAC Unit1','Carrier','XYZ','2021-01-01','Cleaned filters'),
(2,'HVAC Unit2','Trane','ABC','2021-02-01','Replaced fan motor'),
(3,'Chiller','York','123','2021-03-01','Recharged Coolant')

select*from Equipment


-->Create Performance Table
Create table Performance(
Performance_ID int,
Equipment_ID int,
Performance_Date timestamp,
Temperature float,
Humidity float,
Airflow float,
Energy_Consumption float
)

select*from	performance
drop table performance

insert into performance(Performance_ID,Equipment_ID,Performance_Date,Temperature,Humidity,Airflow,Energy_Consumption)
values(1,1,'2023-05-01 08:00:00', 21.5, 45.0, 3000, 50.5),
(2,1,'2023-05-01 08:15:00', 22.0, 42.0, 2900, 49.0),
(3,2,'2023-05-01 08:15:00', 22.0, 42.0, 2900, 49.0),
(4,2,'2023-05-01 08:45:00', 23.0, 38.0, 2700, 46.0),
(5,2,'2023-05-02 09:00:00', 23.5, 36.0, 2600, 44.5),
(6,1,'2023-05-02 09:15:00', 24.0, 34.0, 2500, 43.0),
(7,1,'2023-05-02 09:30:00', 24.5, 32.0, 2400, 41.5),
(8,1,'2023-05-03 09:45:00', 25.0, 30.0, 2300, 40.0),
(9,2,'2023-05-03 10:00:00', 25.5, 28.0, 2200, 38.5),
(10,1,'2023-05-03 10:15:00',  26.0, 26.0, 2100, 37.0),
(11,1,'2023-05-04 10:30:00', 26.5, 24.0, 2000, 35.5),
(12,1,'2023-05-04 10:45:00',  27.0, 22.0, 1900, 34.0),
(13,2,'2023-05-04 11:00:00', 27.5, 20.0, 1800, 32.5),
(14,2,'2023-05-04 11:15:00', 28.0, 18.0, 1700, 31.0),
(15,1,'2023-05-05 11:30:00',  28.5, 16.0, 1600, 29.5),
(16,2,'2023-05-05 11:45:00',  29.0, 14.0, 1500, 28.0),
(17,1,'2023-05-06 12:00:00', 29.5, 12.0, 1400, 26.5),
(18,1,'2023-05-06 12:15:00',  30.0, 10.0, 1300, 25.0),
(19,2,'2023-05-06 12:30:00',  30.5, 8.0, 1200, 23.3)

-->Create table Setpoints
create table Setpoints(
setpoint_ID int,
Equipment_ID int,
Temperature_Setpoint float,
Humidity_Setpoint float,
AirQuality_Setpoint float
)

select*from Setpoints

insert into Setpoints(setpoint_ID,Equipment_ID,Temperature_Setpoint,Humidity_Setpoint,AirQuality_Setpoint)
Values(1,1,70.0,45.0,20.0),
(2,2,72.0,40.0,18.0)

-->Create Control Table
create table control(
	Control_ID int,
	Equipment_ID int,
	Control_Mode varchar(20),
	Fan_speed	int,
	Temperature_Setpoint float
)

insert into control( Control_ID,Equipment_ID,Control_Mode,Fan_Speed,Temperature_Setpoint)
values(1,1,'Auto',2,70.0),
(2,2,'Manual',3,72.0)

--->Create Failures Table
create table Failures(
failure_ID int,
	Equipment_ID int,
	failure_date date,
	failure_description varchar(50)
)

insert into Failures(failure_ID,Equipment_ID,failure_date,failure_description)
Values(1,2,'2020-04-01','Blower motor failure'),
(2,1,'2020-04-15','Control Valve Actuator Failure'),
(3,2,'2020-05-30','VCD Blade damage'),
(4,3,'2021-03-20','Chiller Compressor noise'),
(5,1,'2021-08-13','Filter Choked'),
(6,2,'2021-08-20','DPT signle issue'),
(7,1,'2022-04-09','AHU Leak'),
(8,2,'2023-02-01','Magnehellic Gauge damage')

select*from Equipment
Select*from Performance
select*from Control
select*from Setpoints
select*from failures


