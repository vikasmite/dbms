# dbms
create database exam

use exam
create table student(usn varchar(20) primary key,sname varchar(20),address varchar(20),phone bigint,gender varchar(10));

create table semsec(ssid integer primary key,sem integer,sec varchar(5));
    create table class(usn varchar(20) primary key,ssid integer,foreign key(usn) references student(usn),foreign key(ssid) references semsec(ssid));
    create table course(subcode varchar(20) primary key,title varchar(20),sem integer,credits integer);
    create table iamarks(usn varchar(20),subcode varchar(20),ssid integer,test1 integer,test2 integer,test3 integer,finalia integer,primary key(usn,subcode,ssid),foreign key(usn) references student(usn),foreign key(subcode) references course(subcode),foreign key(ssid) references semsec(ssid));

	  insert into student values('cs101','vikas','manglore',9696500000,'male');
    insert into student values('cs102','praveen','banglore',9496500000,'emale');
    insert into student values('cs103','vignesh','mysore',9696400000,'male');
    insert into student values('cs104','john','manglore',9697500000,'male');
    insert into student values('cs105','mical','banglore',9698500000,'male');


	  insert into semsec values(111,5,'cs1');
    insert into semsec values(112,5,'cs2');
    insert into semsec values(113,5,'cs1');
    insert into semsec values(114,5,'cs1');
    insert into semsec values(115,5,'cs2');
    insert into class values('cs101',113);
    insert into class values('cs102',115);
    insert into class values('cs103',111);
    insert into class values('cs104',112);
    insert into class values('cs105',114);
    insert into course values('18cs51','atc',5,3);
    insert into course values('18cs52','dbms',5,4);
    insert into course values('18cs53','up',5,2);
    insert into course values('18cs54','me',5,3);
    insert into course values('18cs55','cns',5,4);
    insert into iamarks values('cs101','18cs51',113,50,46,47,48);
    insert into iamarks values ('cs101','18cs52',113,40,40,47,42);
    insert into iamarks values('cs101','18cs53',113,50,40,45,45);
    insert into iamarks values('cs101','18cs54',113,40,46,41,42);
    insert into iamarks values('cs101','18cs55',113,50,46,40,45);
    insert into iamarks values('cs103','18cs51',111,45,42,44,44);
    insert into iamarks values('cs103','18cs52',111,41,47,30,44);
    insert into iamarks values('cs103','18cs53',111,38,42,41,45);
    insert into iamarks values('cs103','18cs54',111,35,45,40,40);
    insert into iamarks values('cs103','18cs55',111,39,46,40,42);

	select* from iamarks
