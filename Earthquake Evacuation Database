DROP DATABASE IF EXISTS ShelterDB;
CREATE DATABASE ShelterDB;
USE ShelterDB;

CREATE TABLE Shelters (
  ShelterID INT PRIMARY KEY AUTO_INCREMENT,
  Name VARCHAR(255),
  Location VARCHAR(255),
  MaxCapacity INT,
  AvailabilityStatus VARCHAR(100)
);

CREATE TABLE Residents (
  ResidentID INT PRIMARY KEY AUTO_INCREMENT,
  Name VARCHAR(255),
  Age INT,
  Gender VARCHAR(50),
  MedicalInfo TEXT,
  ShelterID INT,
  FOREIGN KEY (ShelterID) REFERENCES Shelters(ShelterID)
);

CREATE TABLE Managers (
  ManagerID INT PRIMARY KEY AUTO_INCREMENT,
  Name VARCHAR(255),
  ContactNumber VARCHAR(50),
  Email VARCHAR(255) UNIQUE,
  ShelterID INT,
  FOREIGN KEY (ShelterID) REFERENCES Shelters(ShelterID)
);

CREATE TABLE Emergency_Services (
  ServiceID INT PRIMARY KEY AUTO_INCREMENT,
  Type VARCHAR(100),
  ContactInfo VARCHAR(255)
);

CREATE TABLE Manager_Services (
  ManagerID INT,
  ServiceID INT,
  PRIMARY KEY (ManagerID, ServiceID),
  FOREIGN KEY (ManagerID) REFERENCES Managers(ManagerID),
  FOREIGN KEY (ServiceID) REFERENCES Emergency_Services(ServiceID)
);

CREATE TABLE Inventory (
  ItemID INT PRIMARY KEY AUTO_INCREMENT,
  ItemName VARCHAR(255),
  Quantity INT,
  LastUpdated DATETIME,
  ShelterID INT,
  FOREIGN KEY (ShelterID) REFERENCES Shelters(ShelterID)
);

INSERT INTO Shelters (Name, Location, MaxCapacity, AvailabilityStatus)
VALUES 
('Umut Evi', 'Kadıköy, İstanbul', 200, 'Available'),
('Güvenli Yaşam Merkezi', 'Beşiktaş, İstanbul', 150, 'Full'),
('Yeni Hayat Barınağı', 'Üsküdar, İstanbul', 100, 'Available');

INSERT INTO Residents (Name, Age, Gender, MedicalInfo, ShelterID)
VALUES 
('Ayşe Yılmaz', 29, 'Female', 'No known conditions', 1),
('Mehmet Demir', 45, 'Male', 'Diabetic', 2),
('Zeynep Kaya', 36, 'Female', 'Asthma', 3),
('Ali Çelik', 18, 'Male', 'No known conditions', 1),
('Elif Kurt', 50, 'Female', 'Hypertension', 2),
('Ahmet Yıldız', 25, 'Male', 'No known conditions', 3);

INSERT INTO Emergency_Services (Type, ContactInfo)
VALUES 
('Medical', '555-123-4567'),
('Fire', '555-234-5678'),
('Police', '555-345-6789'),
('Mental Health', '555-456-7890');

INSERT INTO Managers (Name, ContactNumber, Email, ShelterID)
VALUES 
('Fatma Aydın', '555-111-2222', 'fatma.aydin@gmail.com', 1),
('Mustafa Koç', '555-222-3333','mustafa.koc@gmail.com', 2),
('Selin Aksoy', '555-333-4444', 'selin.aksoy@n@gmail.com', 3);

INSERT INTO Inventory (ItemName, Quantity, LastUpdated, ShelterID)
VALUES 
('Blankets', 50, NOW(), 1),
('First Aid Kits', 20, NOW(), 2),
('Canned Food', 100, NOW(), 3),
('Water Bottles', 200, NOW(), 1),
('Mattresses', 30, NOW(), 2),
('Clothing Packs', 75, NOW(), 3);

UPDATE Inventory
SET Quantity = 150
WHERE ItemID = 3;
SELECT * FROM Shelters
WHERE Location = 'Kadıköy,Istanbul';
SELECT * FROM Emergency_Services;
SELECT * FROM Managers;
SELECT * FROM Inventory
WHERE Quantity = 200;
