# Title
This project is intended to touch and feel SQL.

# MySQL server setup on Ubuntu
* Step 1: Installing MySQL
```
sudo apt update
sudo apt install mysql-server -y
sudo systemctl start mysql
sudo systemctl status mysql
```
* Step 2: Configuring MySQL
```
sudo mysql_secure_installation
```
* Step 3: Login to MySQL server
```
mysql -u root -p
```
* Step 4: create database with name hacathon and Create a dedicated MySQL user and granting privilges
```
CREATE DATABASE hackathon;
CREATE USER 'hackathon'@'%' IDENTIFIED WITH mysql_native_password BY 'Hackathon@123';
GRANT ALL ON *.* TO 'hackathon'@'%';
FLUSH PRIVILEGES;
```
* Step 5: Create table and perform CRUD operations
```
CREATE TABLE hackathon.teams(
                team_name VARCHAR(25) PRIMARY KEY,
		member1 VARCHAR(25),
		member2 VARCHAR(25),
		member3 VARCHAR(25)
                );
```
```				
INSERT INTO hackathon.teams (
	    team_name,
	    member1,
	    member2,
            member3
	    )
	VALUES
	(
	    'teamA', 
	    'sandeep', 
	    'krishna',
            'rachit'
	) ,
	    (
	        'teamB', 
	        'charan', 
	        'amit',
		'manan'
	    );

```
```
select * from hackathon.teams;
```
```
UPDATE hackathon.teams
SET member1 = 'amit'
WHERE team_name = 'teamA';
```
```
DELETE FROM hackathon.teams
WHERE team_name = 'teamA';
```
# Reference
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04
