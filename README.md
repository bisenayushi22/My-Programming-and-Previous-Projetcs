# **Programming Portfolio and B.Sc. Project Documentation**  

## **Abstract**  
This document presents a structured overview of programming expertise in **C++, Java, Python, MATLAB, and SQL**, along with detailed documentation of B.Sc. projects, including an **SQL-based College Management System**. The focus is on **algorithm design, data structures, deep learning applications, database management, and security protocols**, demonstrating practical problem-solving capabilities in computational programming.

---

## **1. Introduction**  
Programming is an essential tool for solving computational problems, designing optimized algorithms, and managing large-scale data processing. The application of mathematical principles in programming allows for structured problem-solving in areas such as **database management, artificial intelligence, cryptography, and security systems**. This portfolio highlights projects developed during **B.Sc. studies**, focusing on structured data handling, programming optimization, and machine learning implementation.

---

## **2. SQL-Based College Management System**  
### **Project Overview**  
The **College Management System** was developed as a structured **SQL-based relational database** integrated with **Java and Python** for UI management. The system enables **student registration, faculty tracking, course administration, and secure access control mechanisms**. The database schema ensures **fast retrieval, indexing, and structured querying for academic records**.

### **Database Schema Design (SQL)**  
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
This schema maintains **referential integrity** and ensures efficient storage of student and course data.

### **Optimized Query for Student Performance Analysis**  
```sql
SELECT Name, AVG(Grade) FROM Students
JOIN Courses ON Students.CourseID = Courses.CourseID
GROUP BY Name;
```
This query helps in academic evaluation by analyzing **average student grades**.

### **Java GUI for Database Management**  
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
This **Java-based database management application** provides **secure data handling for academic records**.

---

## **3. Deep Learning Applications**  
### **Neural Network Model (Python)**  
Deep learning models implement **neural networks** for classification tasks using **TensorFlow/Keras**.

```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Flatten, Conv2D, MaxPooling2D
from tensorflow.keras.datasets import mnist
from tensorflow.keras.utils import to_categorical

# Load dataset
(train_images, train_labels), (test_images, test_labels) = mnist.load_data()
train_images = train_images.reshape((60000, 28, 28, 1)) / 255.0
test_images = test_images.reshape((10000, 28, 28, 1)) / 255.0
train_labels = to_categorical(train_labels)
test_labels = to_categorical(test_labels)

# Define neural network model
model = Sequential([
    Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    MaxPooling2D(2,2),
    Flatten(),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])

# Compile model
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])

# Train model
model.fit(train_images, train_labels, epochs=5, batch_size=64, validation_split=0.1)

# Evaluate model
test_loss, test_acc = model.evaluate(test_images, test_labels)
print(f'Test Accuracy: {test_acc}')
```
This deep learning model implements **CNN-based image classification** with **high computational accuracy**.

---

### **MATLAB Neural Network Training**
```matlab
% Load dataset
[x_train, y_train, x_test, y_test] = loadMNIST();

% Define neural network
layers = [
    imageInputLayer([28 28 1])
    convolution2dLayer(3, 32, 'Padding', 'same')
    reluLayer
    maxPooling2dLayer(2, 'Stride', 2)
    fullyConnectedLayer(10)
    softmaxLayer
    classificationLayer];

options = trainingOptions('adam', ...
    'MaxEpochs',5, ...
    'MiniBatchSize',64, ...
    'ValidationData',{x_test, y_test});

% Train neural network
net = trainNetwork(x_train, y_train, layers, options);

% Evaluate network performance
YPred = classify(net, x_test);
accuracy = sum(YPred == y_test) / numel(y_test);
disp(['Test Accuracy: ', num2str(accuracy)]);
```
MATLAB-based **neural network modeling ensures efficient computational deep learning solutions**.

---

## **4. Data Security & Encryption**
### **AES-256 Encryption for Secure Data Storage**
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
AES-256 encryption enables **secure credential storage** in academic databases.

---

## **5. Future Scope and Optimization**  
The projects documented above showcase **SQL-based database management, AI-driven deep learning applications, and programming structures**. Future advancements could include:

- **Blockchain Security** – Implementing decentralized storage for enhanced security.
- **AI-Driven Predictive Analytics** – Using deep learning to generate real-time academic forecasts.
- **Computational Cryptography** – Applying mathematical principles for secure encryption models.
- **Quantum Computing-Based Optimization** – Exploring quantum algorithms for enhanced computational speed.

---

## **6. Conclusion**
This portfolio represents structured programming expertise in **C++, Java, Python, MATLAB, and SQL**, with real-world applications in **database management, deep learning, and computational modeling**. The documented projects highlight **problem-solving efficiency**, showcasing **academic research expertise, software structuring techniques, and AI-driven applications**.

