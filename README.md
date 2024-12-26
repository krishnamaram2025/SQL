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
CREATE DATABASE portfolio;
CREATE USER 'portfolio'@'%' IDENTIFIED WITH mysql_native_password BY 'Portfolio@123';
GRANT ALL ON *.* TO 'portfolio'@'%';
FLUSH PRIVILEGES;
```
* Step 5: Create table and perform CRUD operations
```
CREATE TABLE portfolio.skills (
    id INT AUTO_INCREMENT PRIMARY KEY,
    skill_name VARCHAR(25),
    stream_name VARCHAR(25)
);
```
```				
INSERT INTO portfolio.skills (
	    skill_name,
	    stream_name
	    )
	VALUES
	(
	    'FastAPI', 
	    'Development'
	) ,
	  (
	    'AWS', 
	    'Operations'
	) ,
	(
	    'Terraform', 
	    'DevOps'
	);
```
```
select * from portfolio.skills;
```
```
UPDATE portfolio.skills
SET skill_name = 'Docker'
WHERE stream_name = 'DevOps';
```
```
DELETE FROM portfolio.skills
WHERE skill_name = 'Docker';
```
# Reference
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04
