# Blood-Bridge

## DB Setup
CREATE DATABASE bloodbridge;

USE bloodbridge;


CREATE USER 'DBAdmin'@'localhost' IDENTIFIED BY 'bloodbridge';

GRANT SELECT, INSERT, UPDATE, DELETE ON bloodbridge.* TO 'DBAdmin'@'localhost';

FLUSH PRIVILEGES;


CREATE TABLE register (
         id INT AUTO_INCREMENT PRIMARY KEY,
         fullname VARCHAR(255) NOT NULL,
         email VARCHAR(255) NOT NULL UNIQUE,
         password VARCHAR(255) NOT NULL,
         blood_type VARCHAR(10)
     );

CREATE TABLE request (
         id INT AUTO_INCREMENT PRIMARY KEY,
         requester_id INT NOT NULL,
         location VARCHAR(255) NOT NULL,
         blood_type VARCHAR(10) NOT NULL,
         urgency VARCHAR(50),
         date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
         status VARCHAR(50) DEFAULT 'pending',
         FOREIGN KEY (requester_id) REFERENCES register(id) ON DELETE CASCADE
     );

EC2 Commands(use this commands only the first time when accessing the EC2)

sudo yum update -y

sudo yum install python3 -y

sudo yum install python3-pip -y

sudo pip3 install virtualenv

python3 -m venv venv

source venv/bin/activate

pip install flask

sudo yum install git -y

git clone <your repositorie link>

cd <your repository name>

pip install mysql-connector-python

python app.py 



## AWS console 

https://github.com/user-attachments/assets/c279d518-ce56-4ac4-97f7-e0df6e1d5d64




https://github.com/user-attachments/assets/39163397-833d-4427-bfb8-a5e434f5cdaa




https://github.com/user-attachments/assets/8a4d59c2-c077-48f7-9b95-003f4f981347




https://github.com/user-attachments/assets/28d51fab-1487-40a8-9563-e80f858a1400

