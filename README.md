# 🛒 Food-Grocery-Mart

![ASP.NET](https://img.shields.io/badge/ASP.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)

**A complete online grocery shopping platform for seamless food ordering**

## 📖 Overview

A full-featured grocery shopping web application built using **ASP.NET WebForms** and **SQL Server**. This platform enables institutions and customers to deliver online grocery shopping with user enrollment, course management, admin dashboard, and progress tracking with a responsive Bootstrap interface.

---

## ✨ Features

### 🛍️ Customer Portal
- 🔐 **User registration & secure authentication**
- 🔍 **Browse and search products**
- 🛒 **Add to cart functionality**
- 📱 **Responsive design for all devices**
- 📦 **Order placement and tracking**
- 💳 **Multiple payment methods**

### 🎯 Admin Panel
- 📊 **Analytics dashboard**
- 👥 **User & order management**
- 📦 **Product & category management**
- ⚡ **Real-time order status updates**

## 🛠️ Tech Stack

![ASP.NET WebForms](https://img.shields.io/badge/ASP.NET-WebForms-blue)
![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-red)
![Bootstrap](https://img.shields.io/badge/UI-Bootstrap-purple)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)  

---

## 🚀 Installation

### 📋 Prerequisites: XAMPP, PHP 7.4+, MySQL 5.7+

### 1️⃣ Clone Repository

```bash
git clone https://github.com/19JayPatel/FoodMart-Grocery-Website.git
cd FoodMart-Grocery-Website
```

### 2️⃣ Setup Database

- Open phpMyAdmin: http://localhost/phpmyadmin
- Create database: `FoodMart`
- Import: `database/FoodMart.sql`

### 3️⃣ Configure

- Edit `includes/config.php` with your database credentials

### 4️⃣ Launch

```
http://localhost/FoodMart-Grocery-Website
```
---

## 🛢️ Database Schema

Execute the following SQL queries in SQL Server Management Studio to set up the database:

```sql
CREATE DATABASE FoodMart;

CREATE TABLE [dbo].[Admin_tbl] (
    [AdminID]  INT           IDENTITY (1, 1) NOT NULL,
    [Username] VARCHAR (MAX) NOT NULL,
    [Password] VARCHAR (MAX) NOT NULL
);

CREATE TABLE [dbo].[Categories] (
    [CategoryID]   INT            IDENTITY (1, 1) NOT NULL,
    [CategoryName] NVARCHAR (MAX) NOT NULL
);

CREATE TABLE [dbo].[Products_tbl] (
    [ProductID]    INT            IDENTITY (1, 1) NOT NULL,
    [ProductName]  NVARCHAR (MAX) NOT NULL,
    [Weight]       NVARCHAR (MAX) NOT NULL,
    [Price]        NVARCHAR (MAX) NOT NULL,
    [CategoryID]   INT            NOT NULL,
    [CategoryName] NVARCHAR (MAX) NOT NULL,
    [ProductImage] NVARCHAR (MAX) NOT NULL
);

CREATE TABLE [dbo].[User_tbl] (
    [Id]       INT            IDENTITY (1, 1) NOT NULL,
    [FullName] NVARCHAR (MAX) NOT NULL,
    [Email]    NVARCHAR (MAX) NOT NULL,
    [PNumber]  NVARCHAR (MAX) NOT NULL,
    [Password] NVARCHAR (MAX) NOT NULL
);

CREATE TABLE [dbo].[Cart_tbl] (
    [Id]               INT             IDENTITY (1, 1) NOT NULL,
    [User_id]          NVARCHAR (MAX)  NOT NULL,
    [Product_id]       NVARCHAR (MAX)  NOT NULL,
    [Product_name]     NVARCHAR (MAX)  NOT NULL,
    [Product_price]    DECIMAL (10, 2) NULL,
    [Product_quantity] INT             NULL,
    [Product_image]    NVARCHAR (MAX)  NOT NULL,
    PRIMARY KEY CLUSTERED ([Id] ASC)
);

CREATE TABLE [dbo].[Order_tbl] (
    [Order_Id]         INT             IDENTITY (1, 1) NOT NULL,
    [User_Id]          INT             NOT NULL,
    [Order_Date]       DATETIME        NOT NULL,
    [Total_Amount]     DECIMAL (18, 2) NOT NULL,
    [Order_Status]     NVARCHAR (MAX)  NOT NULL,
    [Shipping_Address] NVARCHAR (MAX)  NOT NULL,
    [Payment_Method]   NVARCHAR (MAX)  NOT NULL,
    PRIMARY KEY CLUSTERED ([Order_Id] ASC)
);

CREATE TABLE [dbo].[OrderItems_tbl] (
    [Id]               INT             IDENTITY (1, 1) NOT NULL,
    [Order_Id]         INT             NOT NULL,
    [Product_Name]     NVARCHAR (MAX)  NOT NULL,
    [Product_Price]    DECIMAL (10, 2) NOT NULL,
    [Product_Quantity] INT             NOT NULL,
    [Product_Image]    NVARCHAR (MAX)  NOT NULL,
    PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Insert default admin credentials for Foodmart
INSERT INTO [dbo].[Admin_tbl] ([Username], [Password])
VALUES ('foodmart', 'foodmart123');

```

## 🔑 Default Credentials

### 👨‍💼 Admin: **Username:** `foodmart` | **Password:** `foodmart123`
### 👥 Students: Register at `/user/register.php`

## 🔒 Security

- ✅ Password hashing with `password_hash()`
- ✅ SQL injection prevention
- ✅ Session-based authentication
- ✅ CSRF protection

## 📸 Screenshots

### Home Page
![Home Page](Screenshot/Home.png)

## 👥 Authors

### **Jay Patel**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/19JayPatel)

### **Param Vadher**

[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:paramvadher04@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/param-vadher)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Param-vadher)

## 📄 License

Open source and available for educational purposes.

---

<div align="center">
  
### ⭐ Star this repo if you find it helpful!

Made with ❤️ by Jay Patel & Param Vadher

</div>