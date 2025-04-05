show databases;
use studentmanagement;
show tables;
create table studentst6(
StudentID int auto_increment primary key,
Name varchar(100) not null,
science_score int check(science_score between 0 and 100),
total_score int
);

insert into studentst6 (Name, science_score, total_score)
values
('Dawn',75,85),
('kiran',79,79),
('sasi',82,80),
('Manoj',84,88),
('Rahul',87,87),
('Nikhil',77,77),
('Rana',71,81),
('Gladis',76,66),
('Nitiya',80,80),
('Mounika',55,75);


SELECT 
    StudentID, 
    Name, 
    science_score, 
    total_score, 
    RANK() OVER (ORDER BY total_score DESC) AS student_rank
FROM studentst6;

Select 
	StudentID,
    Name,
    science_score,
    SUM(science_score) over (order by StudentID) as running_total
FROM studentst6;
