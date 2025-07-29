# 📚 Library Management System – SQL Server Project

This is a relational database project developed in **SQL Server** to simulate a **Library Management System**. It includes the creation of a complete schema, population of tables with realistic sample data, and various stored procedures to query and manage the data efficiently.

---

## 🚀 Features

- Database schema creation using `CREATE DATABASE`, `CREATE TABLE`, and foreign key constraints.
- Sample data insertion for:
  - Publishers
  - Books
  - Library branches
  - Borrowers
  - Book loans
  - Book copies
  - Book authors
- Stored procedures for querying:
  - Books available at specific branches
  - Borrowers with/without loans
  - Due date tracking
  - Books by specific authors
  - Loans summary per branch
  - Books checked out by frequent borrowers

---

## 🛠 Technologies Used

- **SQL Server**
- **T-SQL (Transact-SQL)**

---

## 📂 Database Structure

### Tables:

- `tbl_publisher` – Publisher information
- `tbl_book` – Book records linked to publishers
- `tbl_library_branch` – Library branch details
- `tbl_borrower` – Borrower personal details
- `tbl_book_loans` – Tracks book checkouts and due dates
- `tbl_book_copies` – Number of book copies available in each branch
- `tbl_book_authors` – Author details for books

### Relationships:

- `tbl_book` → `tbl_publisher`
- `tbl_book_loans` → `tbl_book`, `tbl_library_branch`, `tbl_borrower`
- `tbl_book_copies` → `tbl_book`, `tbl_library_branch`
- `tbl_book_authors` → `tbl_book`

---

## 🔍 Sample Stored Procedures

1. `bookCopiesAtAllSharpstown` – Total copies of a book in **Sharpstown** branch.
2. `bookCopiesAtAllBranches` – Copies of a book across all branches.
3. `NoLoans` – Borrowers who have **no books checked out**.
4. `LoanersInfo` – Borrower info for books due today at **Sharpstown**.
5. `TotalLoansPerBranch` – Number of books loaned out per branch.
6. `BooksLoanedOut` – Borrowers who checked out **more than 5 books**.
7. `BookbyAuthorandBranch` – Book copies by **Stephen King** at **Central** branch.

---

## 📦 How to Run

1. Open **SQL Server Management Studio (SSMS)**.
2. Create a new query window and paste the full script from this repository.
3. Execute the script to:
   - Create the database and tables
   - Insert all sample data
   - Create stored procedures
4. Use `EXEC` to run any stored procedure.

---

## 🧪 Example Queries

```sql
-- Get book copies of "The Lost Tribe" at Sharpstown
EXEC dbo.bookCopiesAtAllSharpstown;

-- Borrowers with more than 5 books
EXEC dbo.BooksLoanedOut;
