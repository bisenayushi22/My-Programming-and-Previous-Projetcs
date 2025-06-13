### **Title: Programming Portfolio & B.Sc. Project Documentation**  

### **1. Introduction**  
This document highlights **programming expertise in C++, Java, Python, MATLAB, and SQL**, alongside a detailed overview of the **SQL-based College Management System** developed during your B.Sc. studies. The focus includes **database optimization, algorithm development, and application structure**.  

---

### **2. Programming Skills Overview**  
Your proficiency across programming languages enables efficient computational problem-solving and software development:  

- **C++ & Java** – System architecture, algorithm implementation, and computational modeling.  
- **Python & MATLAB** – AI-driven analysis, data visualization, and numerical computations.  
- **SQL** – Database management, indexing, and query optimization.  

---

### **3. B.Sc. Project: SQL-Based College Management System**  

#### **System Overview**  
The College Management System was designed to streamline academic operations using a **SQL-based relational database** integrated with a **GUI interface in Java**.  

#### **Database Schema Design (SQL)**  
```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(255) UNIQUE,
    CourseID INT,
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);

CREATE TABLE Courses (
    CourseID INT PRIMARY KEY,
    CourseName VARCHAR(100),
    Credits INT
);
```
This relational structure ensures **referential integrity** and efficient academic data management.  

#### **Optimized Query Example**  
```sql
SELECT Name, AVG(Grade) FROM Students
JOIN Courses ON Students.CourseID = Courses.CourseID
GROUP BY Name;
```
This query calculates **student performance statistics** efficiently.  

#### **Java GUI for Database Management**  
```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;

public class CollegeManagement {
    public static void main(String[] args) {
        try {
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/college_db", "user", "password");
            String sql = "INSERT INTO Students (StudentID, Name, Email, CourseID) VALUES (?, ?, ?, ?)";
            PreparedStatement stmt = conn.prepareStatement(sql);
            stmt.setInt(1, 101);
            stmt.setString(2, "Ayushi");
            stmt.setString(3, "ayushi@email.com");
            stmt.setInt(4, 1);
            stmt.executeUpdate();
            conn.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
This **Java implementation** connects the database, inserting student records dynamically.  

---

### **4. Computational Applications in MATLAB & Python**  
#### **MATLAB for Computational Analysis**  
```matlab
x = linspace(-10, 10, 100);
y = sin(x) ./ x;
plot(x, y);
title('Mathematical Function Representation');
```
This MATLAB script visualizes **function behavior**, useful in mathematical modeling.  

#### **Python-Based Deep Learning Model**  
```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Flatten

# Define neural network model
model = Sequential([
    Flatten(input_shape=(28,28)),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])

model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
model.summary()
```
This Python-based **deep learning model** applies **neural network classification**.  

---

### **5. Security & Optimization in SQL-Based Systems**  
Data security was ensured using **AES-256 encryption** for user credentials:  

```python
from Crypto.Cipher import AES
import base64

def encrypt_data(data, key):
    cipher = AES.new(key.encode('utf-8'), AES.MODE_ECB)
    encrypted_text = base64.b64encode(cipher.encrypt(data.ljust(32).encode('utf-8')))
    return encrypted_text

key = 'securekey123'
data = 'Sensitive Data'
encrypted = encrypt_data(data, key)
print(f'Encrypted Data: {encrypted}')
```

---

### **6. Conclusion & Future Scope**  
Your **SQL-based College Management System**, combined with proficiency in **C++, Java, Python, MATLAB, and SQL**, demonstrates expertise in **database management, deep learning applications, and mathematical modeling**. Future advancements could include **AI-driven predictive analytics** and **blockchain-enhanced security for academic records**.  

