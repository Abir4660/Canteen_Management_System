# ☕ Round Cafe – Oracle APEX Canteen Management System
**Round Cafe** is a full-stack **Oracle APEX application** designed to manage a canteen or café.  
It integrates **authentication, menus, orders, items, and payments**, along with **custom HTML/CSS styling** for an attractive UI.

---

## 🚀 Project Overview

This system is built using:
- **Oracle APEX 24.2.8**
- **PL/SQL** (for backend logic, functions, triggers)
- **HTML/CSS** (for UI customization)
- **Oracle Database** (for persistent storage)

It provides a complete canteen workflow — from user login and order creation to payment validation.

---

## 🧩 Key Features

| Feature | Description |
|----------|--------------|
| 🔐 **Authentication System** | Secure login for Admins and Customers using custom APEX authentication. |
| 👤 **User Management** | Admins can add, edit, or remove users with roles `ADMIN` or `CUSTOMER`. |
| 🍴 **Menu Management** | Manage available food/drink items, prices, and availability. |
| 🧾 **Orders and Items** | Place orders, view order details, and calculate totals dynamically. |
| 💳 **Payments** | Automatic payment validation via trigger and real-time status updates. |
| 🧠 **SQL Backend Logic** | Includes function `GET_ORDER_TOTAL` and trigger `TRG_VALIDATE_PAYMENT`. |
| 🎨 **Custom UI** | Custom CSS for modern layout, blurred backgrounds, and responsive design. |
| 📱 **Progressive Web App (PWA)** | Can be installed and run like a mobile app (PWA enabled). |

---

## 🗂️ Application Details

| Property | Value |
|-----------|--------|
| **Application Name** | Round Cafe |
| **App ID** | 214056 |
| **Pages** | 14 |
| **Regions** | 25 |
| **Processes** | 20 |
| **Dynamic Actions** | 10 |
| **Authentication Schemes** | 2 |
| **Authorization Scheme** | 1 |
| **Theme** | Universal Theme (42) |
| **Version** | Release 1.0 |

---

## 🧱 Database Schema

This app uses the following main database tables:

- `USERS` – stores login credentials and roles  
- `MENU` – holds available items and prices  
- `ORDERS` – customer orders  
- `ORDER_ITEMS` – links orders and menu items  
- `PAYMENTS` – records transactions
- 'Change Authentication' - Change Username And Password

👉 Full SQL setup is available in [`canteen_schema.sql`](./canteen_schema.sql)

---

## ⚙️ Backend Logic (PL/SQL)

### Function: `GET_ORDER_TOTAL(p_order_id NUMBER)`
Calculates total order amount by summing menu item prices.

### Trigger: `TRG_VALIDATE_PAYMENT`
Before inserting or updating payments:
- Validates payment amount against total  
- Calculates and stores change  
- Updates order status automatically to `SERVED`

---

## 🎨 Frontend (HTML & CSS)

Custom UI modifications include:
- Blurred café logo background on login page  
- Rounded cards and soft shadows for menus  
- Gradient buttons for actions (Order, Payment, etc.)  
- Responsive design for mobile and tablet views  

> The app uses a modified **Universal Theme 42** with custom CSS loaded via APEX Static Files.

---

## 🔐 Authentication

Two authentication schemes are defined:
1. **Custom Authentication** – Manual login with `USERNAME` and `PASSWORD`
2. **APEX Built-In Authentication** – for workspace-level users

**Roles:**
- `ADMIN` – Full access to all pages  
- `CUSTOMER` – Limited to placing orders and making payments  

---

## 🧭 Navigation Structure

| Page | Description |
|------|--------------|
| **Home (1)** | Welcome page with summary |
| **Users (2)** | Manage system users |
| **Menu (4)** | Add, edit, and manage food items |
| **Orders (6)** | View and update orders |
| **Items (8)** | Manage individual ordered items |
| **Payments (10)** | Process and view payments |
| **Change Authentication (12)** | Switch authentication scheme |

---

## 🖥️ Installation Guide

### 1. Import APEX Application
1. Open **Oracle APEX → App Builder**
2. Click **Import**
3. Select the file [`f214056.sql`](./f214056.sql)
4. Choose **Install Supporting Objects** when prompted
5. Run the app as **Admin**

### 2. Run Database Script
Run the SQL script in your workspace schema:
```sql
@canteen_schema.sql

3. Log In
Default roles:

Admin: Create users, menus, change username and password and manage all data

Customer: Place orders and make payments

