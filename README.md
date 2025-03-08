<!--# InternetBankingFullStackApp
This repository contains the source code for a full stack Internet Banking Application. The application provides a comprehensive solution for managing user details, accounts, transactions, and other related functionalities.
Here's the markdown code for your README file:-->

# Internet Banking Application - Bank of Anushka

<img width="936" alt="{637943D0-B1D9-499C-8089-B745060B7856}" src="https://github.com/user-attachments/assets/34b12572-1d32-4b1d-bf82-5b0367d2aa90" />

## 📌 Overview
The Internet Banking Application is a Spring Boot microservices-based system with a React frontend that enables users to register, log in, create bank accounts, and perform transactions like withdrawals, deposits, and fund transfers. The system also allows users to view transaction history and check their account balance.

## 🚀 Features

### User Features
- ✔ User Registration & Authentication (JWT-based login)
- ✔ Account Creation
- ✔ Deposit, Withdraw & Fund Transfer
- ✔ Transaction History
- ✔ Check Account Balance
- ✔ Secure Logout

### Admin Features
- ✔ View All User Accounts
- ✔ Access All API Endpoints

## 🛠️ Tech Stack

| Layer          | Technology Used                      |
|----------------|--------------------------------------|
| Frontend       | React.js, Bootstrap, Axios           |
| Backend        | Spring Boot, Spring Security, Hibernate, REST API |
| Database       | PostgreSQL / MySQL                   |
| Authentication | JWT (JSON Web Token)                 |
| API Gateway    | Spring Cloud Gateway                 |
| Service Discovery | Eureka Server                     |
| Containerization | Docker                             |
| Deployment     | Kubernetes (Optional)                |

## 🖼️ Architecture Diagram
The Internet Banking System follows a microservices-based architecture where each service is independent and communicates via REST APIs.
![bank-microservices](https://github.com/user-attachments/assets/6562018e-1670-4540-94c7-0f3c2bc2bbd8)

## 📌 Architecture Overview
```
                          +----------------------------+
                          |        React Frontend      |
                          |   (User Registration, UI)  |
                          +----------------------------+
                                      |
                                      v
                          +----------------------------+
                          |   API Gateway (Spring Cloud) |
                          +----------------------------+
                                      |
       +---------------------------------------------------------+
       |                           Backend Services              |
       |---------------------------------------------------------|
       | 1️⃣ Banking Core Service  |  Handles core banking logic |
       | 2️⃣ Payment Service       |  Manages transactions        |
       | 3️⃣ Fund Transfer Service |  Handles money transfers     |
       | 4️⃣ User Service         |  Manages user authentication |
       | 5️⃣ Transaction Service  |  Stores transaction history  |
       +---------------------------------------------------------+
                                      |
                          +----------------------------+
                          |   Database (MySQL)    |
                          +----------------------------+
```

## 📂 Folder Structure

### 📌 Frontend (React)
```
📦 internet-banking-frontend
┣ 📂 public
┣ 📂 src
┃ ┣ 📂 assets                # Images, icons, etc.
┃ ┣ 📂 components            # UI components (Navbar, Footer)
┃ ┣ 📂 pages                 # Pages (Home, Login, Register, Dashboard)
┃ ┣ 📂 services              # Axios API calls
┃ ┣ 📂 utils                 # Helper functions, JWT handling
┃ ┣ 📜 App.js                # Main React app
┃ ┣ 📜 index.js              # Entry point
┗ 📜 package.json            # Dependencies
```

### 📌 Backend (Spring Boot)
```
📦 internet-banking-backend
┣ 📂 banking-core-service
┣ 📂 payment-service
┣ 📂 fund-transfer-service
┣ 📂 user-service
┣ 📂 transaction-service
┣ 📂 api-gateway
┣ 📂 service-registry (Eureka)
┗ 📜 pom.xml                # Maven dependencies
```

<!--## 📸 Screenshots
(Add actual screenshots here)

| Feature            | Screenshot         |
|--------------------|--------------------|
| Home Page          | !Home Page |
| User Registration  | !User Registration |
| Login Page         | !Login Page |
| Dashboard          | !Dashboard |
| Transaction History| !Transaction History |-->

## 🔧 Setup and Installation

### 📌 Backend Setup (Spring Boot)
1️⃣ Clone the repository
```bash
git clone https://github.com/anushkaisnotlazy/Internet-Banking-Microservices-Project.git
cd internet-banking-backend
```
2️⃣ Configure `application.properties` (PostgreSQL/MySQL)
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/bank_db
spring.datasource.username=root
spring.datasource.password=your_password
```
3️⃣ Build & Run the backend
```bash
mvn clean install
mvn spring-boot:run
```

### 📌 Frontend Setup (React)
1️⃣ Go to frontend folder
```bash
cd .\anushka-bank\
```
2️⃣ Install dependencies
```bash
npm install
```
3️⃣ Run the React app
```bash
npm start
```
App will run at http://localhost:3000 by default

## 📡 API Endpoints

### User Authentication
| Method | Endpoint        | Description         |
|--------|-----------------|---------------------|
| POST   | /auth/new  | Register new user   |
| POST   |/auth/authenticate     | User login (JWT)    |

### User Service
| Method | Endpoint            | Description             |
|--------|---------------------|-------------------------|
| POST   | users/register     | Create a new user account|
| GET    | users/accountNumber/{userId}       | Get account details     |
| GET    | /users/{id}| Get account balance     | Get user by ID    |
| PUT    |/users/{id}| Get AccountDTO by User ID|
|DELETE|/users/delete/{id}| Delete User||
| GET    |/users/all      | Get account details     |

### Transaction Service
| Method | Endpoint                | Description             |
|--------|-------------------------|-------------------------|
| POST   | /transactions/addmoney    | Deposit money           |
| POST   | /transactions/withdraw   | Withdraw money          |
| POST   | /transactions/transfer   | Transfer funds          |
| GET    | /transactions/{accountNumber}| Get transaction history |

### Account Service
| Method | Endpoint                | Description             |
|--------|-------------------------|-------------------------|
| POST   |   accounts/register  |   Register Account        |
| PUT   | accounts/addBalance/{accountNumber}/{amount}   | Deposit money          |
| PUT   | accounts/deductBalance/{accountNumber}/{amount}   | Withdraw money          |
| GET    | accounts/{email} |  Get user by email |
| GET    | accounts/{accountNumber}| Get transaction history |
| GET    | accounts/balance/{accountNumber}| Get Balance by Account Number |


## 🔒 Security Features
- ✔ JWT-based Authentication
- ✔ Role-based Access Control (Admin/User)
- ✔ Password Hashing (BCrypt)

## 🎯 Future Enhancements
- ✅ Implement Two-Factor Authentication (2FA)
- ✅ Add Admin Dashboard
- ✅ Deploy on AWS/GCP with Kubernetes

## 👨‍💻 Contributors
- **Anushka Saxena**
  
## 📜 License
This project is licensed under the MIT License.
