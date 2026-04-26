# 🏦 Bank Client Management System

A console-based bank management system built in **C++** as part of Dr. Mohamed Abu Hadhood's C++ roadmap.  
The system manages bank clients and users through a **file-based storage** approach using structured text files.

---

## 📋 Features

### 👤 Client Management
| Feature | Description |
|---|---|
| List Clients | Display all clients in a formatted table with balances |
| Add Client | Add new clients with full validation (unique account number, phone format, PIN range) |
| Delete Client | Find and delete a client after confirmation |
| Update Client | Modify any client's data |
| Find Client | Search for a client by account number |

### 💰 Transactions
| Feature | Description |
|---|---|
| Deposit | Add funds to any client account |
| Withdraw | Withdraw funds with balance validation (max 3 failed attempts) |
| Total Balances | View all balances with a running total |

### 🔐 User Management
| Feature | Description |
|---|---|
| List Users | Display all system users and their permission levels |
| Add User | Create new users with custom permission settings |
| Delete User | Remove users (Admin account is protected) |
| Update User | Modify user credentials and permissions |
| Find User | Search for a user by username |

### 🛡️ Permissions System
Each user is assigned a permission value built using **bitwise operations**:

| Permission | Value |
|---|---|
| Show Client List | 1 |
| Add New Clients | 2 |
| Delete Client | 4 |
| Update Client | 8 |
| Find Client | 16 |
| Transactions | 32 |
| Manage Users | 64 |
| Full Access (Admin) | -1 |

> Permissions are combined by adding their values. For example, a user with List + Add + Find = 1 + 2 + 16 = **19**.

---

## 🗂️ Data Storage

All data is stored in plain text files using `#//#` as a field separator.

**`BankClients.txt`** — stores client records:
```
A100#//#2002#//#Farida Mahmoud#//#01222263457#//#797000000.000000
```
Fields: `AccountNumber #//# PinCode #//# Name #//# PhoneNumber #//# Balance`

**`Users.txt`** — stores user records:
```
Admin#//#1111#//#-1
```
Fields: `UserName #//# Password #//# Permission`

---

## 🔒 Login & Access Control

- The system starts with a **Login Screen**
- A default `Admin` account (`Admin` / `1111`) is auto-created if it doesn't exist
- Each operation is checked against the logged-in user's permission before execution
- Users without permission see an **Access Denied** screen

---

## 🛠️ Tech Stack

- **Language:** C++
- **Libraries:** `<iostream>`, `<fstream>`, `<vector>`, `<string>`, `<iomanip>`
- **Concepts used:** Structs, Vectors, File I/O, Enums, Bitwise Operations, Input Validation, Recursion-free modular design

---

## 🚀 How to Run

### Requirements
- Any C++ compiler (GCC, MSVC, Clang)
- Windows (uses `system("cls")` and `system("pause")`)

### Steps
1. Clone the repository
   ```bash
   git clone https://github.com/farida285/Bank-Client-Management-System
   ```
2. Compile the source file
   ```bash
   g++ "BankProject.cpp" -o BankSystem
   ```
3. Run the executable
   ```bash
   ./BankSystem
   ```
4. Login with the default admin credentials:
   - **Username:** `Admin`
   - **Password:** `1111`

> `BankClients.txt` and `Users.txt` are **automatically created on first run** — no need to create them manually.  
> The same `BankClients.txt` file is also used by the [ATM System](https://github.com/farida285/ATM-System).

---

## 📁 Project Structure

```
bank-management-system/
│
├── BankProject.cpp   # Main source file
├── BankClients.txt               # Client data (auto-generated)
├── Users.txt                     # User data (auto-generated)
└── README.md
```

---

## 🙋‍♀️ Author

**Farida** — Communications Engineering Graduate  
📌 Part of Dr. Mohamed Abu Hadhood's C++ roadmap — Course 7 & 8  
🔗 [GitHub](https://github.com/farida285)
