CREATE DATABASE PROJECT;

CREATE TABLE Person(

    workerID INTEGER NOT NULL,

    fname VARCHAR(11),

    lname VARCHAR(11),

    salary INTEGER,

    sectorID INTEGER NOT NULL,

    manager INTEGER,

    sex INTEGER,

    DOB DATE,

    marketID INTEGER,

    PRIMARY KEY(workerID),

    FOREIGN KEY(sectorID) REFERENCES Works_on(secNO),

    FOREIGN KEY(sectorID) REFERENCES workerID

);

 

 

CREATE TABLE Market(

    marketID INTEGER NOT NULL,

    name VARCHAR(11),

    M_manager INTEGER,

    PRIMARY KEY(marketID),

    FOREIGN KEY(M_manager) REFERENCES Person(workerID)

)

 

CREATE TABLE Sector(

    sectorID INTEGER NOT NULL,

    sname VARCHAR(11),

    location INTEGER,

    mID INTEGER,

    PRIMARY KEY(sectorID),

    FOREIGN KEY(mID) REFERENCES Market(marketID),

    FOREIGN KEY(location) REFERENCES location(loID)

)

 

CREATE TABLE Works_on(

    time INTEGER,

    secNO INTEGER,

    workerNO INTEGER,

    FOREIGN KEY(sectorNO) REFERENCES Sector(sectorID),

    FOREIGN KEY(workerNO) REFERENCES Person(workerID)

)

 

CREATE TABLE Location(

    loID INTEGER NOT NULL,

    LOname VARCHAR(11)

    PRIMARY KEY(loID)

)

 

CREATE TABLE Located_in(

    Market INTEGER,

    Location INTEGER,

    FOREIGN KEY(Market) REFERENCES Market(marketID),

    FOREIGN KEY(Location) REFERENCES Location(loID)

)

 

 

SAMPLE QUERY

INSERT INTO Person VALUES ('1','Bar','Foo',1231,1,1,1,"1976-11-04",1);

SELECT * FROM PERSON WHERE manager="1";

UPDATE ON Location SET LOname="Alepa" WHERE loID="1";

DELETE FROM Person WHERE workerID ="2"
