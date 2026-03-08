This is a Python-based **Library/Book Shop Management System** that uses a **MySQL** backend to handle inventory, user authentication, and sales tracking. It features a command-line interface (CLI) for managing book stocks, processing customer purchases, and visualizing monthly sales.

---

## 🚀 Features

* **User Authentication:** Secure login and registration for staff/admins.
* **Inventory Management:** Add new titles, update existing stock levels, and view current availability.
* **Automated Book Numbering:** Generates unique IDs for new book entries.
* **Sales Processing:** Records customer details, updates stock levels automatically, and generates a printable `.txt` receipt.
* **Data Visualization:** Generates a bar chart of monthly sales using Matplotlib.
* **Database Integration:** Persistent storage using MySQL with relational table structures.

---

## 🛠️ Prerequisites

Before running the application, ensure you have the following installed:

* **Python 3.x**
* **MySQL Server**
* **Required Python Packages:**
```bash
pip install mysql-connector-python matplotlib

```



---

## 📂 Project Structure

| File | Description |
| --- | --- |
| `Tables_in_mysql.py` | **Setup Script:** Creates the database (`shop_management`), tables, and default admin user. |
| `Book.py` | **Core Logic:** Contains all backend functions, database queries, and business logic. |
| `Main.py` | **Entry Point:** The CLI menu-driven interface to interact with the system. |

---

## ⚙️ Setup & Installation

1. **Database Configuration:**
Open `Tables_in_mysql.py` and `Book.py`. Ensure the MySQL connection details (host, user, password) match your local MySQL setup:
```python
# Example connection string
cntr.connect(host='localhost', user='root', passwd='your_password')

```


2. **Initialize the Database:**
Run the setup script once to create the necessary tables and schema:
```bash
python Tables_in_mysql.py

```


3. **Launch the App:**
Start the management system:
```bash
python Main.py

```



---

## 📊 Database Schema

* **Stock:** Stores book details, pricing, and current stock counts.
* **Users:** Stores credentials for system access.
* **Purchased:** Tracks transaction history linked to the stock via `Book_No`.

---

## ⚠️ Important Notes

* **Default Login:** The setup script creates a default user:
* **Username:** `admin`
* **Password:** `admin@123`


* **Printing:** The `sell_book` function attempts to use the Windows `startfile(filename, 'print')` command. This may need adjustment if running on macOS or Linux.
* **Stock Depletion:** The system is configured to automatically delete a book record from the `stock` table once the `Available_Stock` reaches zero.
