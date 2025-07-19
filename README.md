# Add Buyers Module
This project is a simple *Java Swing-based desktop application* developed using *NetBeans IDE* and connected to a *MySQL database* using *MySQL Workbench*. The module allows users to add buyer details (name, contact number, email, address, gender) to the database.
---

## 💻 Technologies Used
- Java (Swing GUI)
- NetBeans IDE
- MySQL Workbench
- JDBC (Java Database Connectivity)

## 📁 Folder Structure
AddBuyersModule/ ├── src/ │   ├── project/ │   │   └── ConnectionProvider.java │   └── AddBuyersFrame.java ├── database/ │   └── meowiee.sql └── README.md

## 🗃 Database Setup
1. *Open MySQL Workbench*.
2. Create a new database:
      CREATE DATABASE meowiee;
3. Select the database:
      USE meowiee;
4. Create the buyers table:
    CREATE TABLE buyers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    contact_number VARCHAR(20),
    email VARCHAR(100),
    address TEXT,
    gender VARCHAR(10)
    );

🔌 Database Connection
File: ConnectionProvider.java
This file handles the connection between the Java application and the MySQL database.

package project;
import java.sql.Connection;
import java.sql.DriverManager;

public class ConnectionProvider {
    public static Connection getCon() {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            return DriverManager.getConnection("jdbc:mysql://localhost:3306/meowiee", "root", "your_password");
        } catch (Exception e) {
            e.printStackTrace();
            return null;
        }
    }
}

> ⚠ Replace "your_password" with your MySQL root password.


🧾 How to Run
1. Open the project in NetBeans.
2. Ensure your MySQL server is running.
3. Edit ConnectionProvider.java with your own database credentials.
4. Run the AddBuyersFrame class.
5. Enter buyer details and click Save.
6. Data will be inserted into the buyers table in the meowiee database.

✅ Features
Add buyer with validation
Save to MySQL database
Reset form fields



---

📌 Notes

Ensure the JDBC driver is included in the project's libraries.
You may use JOptionPane to display success/failure messages.
Make sure your MySQL server is running on port 3306.
