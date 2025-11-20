# Flask-signup-app_CSC-312
```markdown
# Flask Signup Web Application

This is a **simple Flask web application** built for the MIVA-CSC312 Tutor-Marked Assessment.  
It allows users to sign up with a username and password, storing the credentials securely in a MySQL database.

---

## 📝 Features

- **Homepage**: Basic homepage built using HTML and Bootstrap.
- **Signup Page**: Form for users to register with a username and password.
- **Database Integration**: MySQL database (`mydb`) with table `tbl_user`.
- **Password Security**: Passwords are hashed before being stored in the database.
- **Timestamp Tracking**: Each signup is automatically timestamped in the database.

---

## 📂 Project Structure

```

flask_app/
│ app.py                  # Main Flask application
│ requirements.txt        # Python dependencies
└───templates/
│ index.html          # Homepage
│ signup.html         # Signup form page

````

---

## ⚙️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/YourUsername/YourRepoName.git
cd YourRepoName
````

### 2. Install Dependencies

Make sure you have Python installed (>=3.8).
Then install required packages:

```bash
pip install -r requirements.txt
```

### 3. Set Up MySQL Database

1. Open phpMyAdmin or MySQL Workbench.
2. Run the following SQL script:

```sql
CREATE DATABASE IF NOT EXISTS mydb;

USE mydb;

CREATE TABLE tbl_user (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100) NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

3. Update your MySQL credentials in `app.py` if necessary:

```python
db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",   # replace with your MySQL password
    database="mydb"
)
```

### 4. Run the Application

```bash
python app.py
```

Visit (http://127.0.0.1:5000/signup) in your browser.

---

## 🔐 Password Security

* Uses `werkzeug.security.generate_password_hash()` for hashing passwords.
* Passwords are stored in the database in hashed format — not readable as plain text.

---

## 👥 Collaborators

* After cloning the repo, collaborators should install dependencies and set up their local MySQL database to run the app.

---

## 📄 Notes

* All HTML files are located in the `templates/` folder.
* The database automatically stores the signup timestamp (`created_at`).
* Ensure the MySQL server is running before starting the Flask app.

