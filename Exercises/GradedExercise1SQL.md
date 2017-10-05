.headers on

--GradedExercise1

--SQL

--Name: Xavier Kleiber


drop table if exists drivetime;

create table drivetime(
	id int PRIMARY KEY,
	date text,
	departure int,
	arrival int
);

insert into drivetime values (1, "2017-08-07", 0700, 0730);
insert into drivetime values (2, "2017-08-08", 0705, 0736);
insert into drivetime values (3, "2017-08-09", 0715, 0756);
insert into drivetime values (4, "2017-08-10", 0713, 0754);
insert into drivetime values (5, "2017-08-11", 0703, 0732);
insert into drivetime values (6, "2017-08-14", 0710, 0739);

select date, (arrival - departure) as time from drivetime;
date|time
2017-08-07|30
2017-08-08|31
2017-08-09|41
2017-08-10|41
2017-08-11|29
2017-08-14|29