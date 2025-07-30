# 📚 Library Management System Dashboard

This project is a **Power BI dashboard** designed to visualize and analyze key insights from a **Library Management System** built with **MySQL**.

---

## 📊 Dashboard Overview

The dashboard helps track:

- ✅ Total Books Issued and Returned
- 📌 Books Distribution by Genre
- 🏬 Number of Loans per Branch
- 👥 Active Borrowers and Loan Activity

---

## 🛠️ Tech Stack

- 💻 **MySQL Workbench** – For database design and record insertion
- 📊 **Power BI Desktop** – For data visualization and reporting
- 📂 `.pbix` file – Contains the complete report

---

## 🧾 Database Structure

This project uses the following 4 main tables:

| Table Name  | Description |
|-------------|-------------|
| `books`     | Stores book details (title, author, genre, publisher) |
| `borrowers` | Contains member details (name, contact) |
| `branches`  | List of library branches |
| `loans`     | Records book issue/return transactions |

Each table contains **100+ records**, created using SQL `INSERT` scripts.

---

## 🧩 Key Visuals in the Dashboard

1. **Books Issued & Returned**  
   - KPIs showing number of books issued and returned

2. **Books by Genre**  
   - Bar or donut chart showing number of books per genre

3. **Loans per Branch**  
   - Column chart showing loan activity per library branch

4. **Borrowers Activity**  
   - Table or slicer with active members and their loan status

---

## ⚙️ Setup Instructions

### 🔹 Step 1: MySQL Database
- Create the database and tables using the provided `.sql` script
- Import 100 records per table using `INSERT INTO` statements

### 🔹 Step 2: Connect Power BI to MySQL
- Go to **Home → Get Data → MySQL**
- Enter credentials and connect to the `libm` database
- Load all four tables

### 🔹 Step 3: Build Relationships
- Ensure relationships are set in **Model View**, such as:
  - `loans.book_id` → `books.book_id`
  - `loans.borrower_id` → `borrowers.borrower_id`
  - `loans.branch_id` → `branches.branch_id`

### 🔹 Step 4: Create Visuals
- Add KPIs, bar charts, column charts, slicers
- Use calculated measures such as:
  ```DAX
  IssuedBooks = CALCULATE(COUNT(loans[loan_id]), loans[status] = "Issued")
  ReturnedBooks = CALCULATE(COUNT(loans[loan_id]), loans[status] = "Returned")
AUTHOR: Mr.Faiz
