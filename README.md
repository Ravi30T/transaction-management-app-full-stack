# **Transaction Management System**

## **Frontend**

A feature-rich web application for managing user transactions. It provides seamless transaction tracking, secure user authentication, and intuitive profile management. Built with **React.js** and backed by a robust API.

---

## **Features**

### **User Authentication**
- Register and login with secure JWT-based authentication.
- Protected routes to safeguard user data.

### **User Profile**
- View user details such as User ID, email, and account balance.
- Logout functionality for enhanced security.

### **Transaction Management**
- Access detailed transaction history.
- Dynamically update transaction statuses.
- Fully responsive design for optimal performance on all devices.

### **Routing**
- Intuitive and user-friendly navigation powered by React Router.

---

## **Technologies Used**

### **Frontend**
- **React.js**: Core frontend framework.
- **React Router**: Enables smooth navigation.
- **`js-cookie`**: Manages authentication tokens.
- **`react-loader-spinner`**: Provides interactive loading animations.
- **CSS**: Ensures responsive and aesthetic design.

### **Backend**
- RESTful API for authentication and transaction management.

---

## **Installation and Setup**

### **Prerequisites**
- Node.js installed
- A package manager (`npm` or `yarn`)

### **Steps**

## 1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <project-directory>
  ```
### 2. Install dependencies:
```bash
npm install
```
### 3. Create a .env file in the root directory with the following content:
```bash
DB_USER=<your-db-user>
DB_PASSWORD=<your-db-password>
DB_CLUSTER=<your-db-cluster>
DB_NAME=<your-database-name>
JWT_SECRET=<your-jwt-secret>
```
### 4. Start the server:
```bash
node <file-name>.js
```
Replace <file-name> with the name of your server file.

## API Endpoints
### 1. Register New User
- Endpoint: /register
- Method: POST
- Request Body:
```bash
{
  "username": "Ravi",
  "email": "ravi@gmail.com",
  "password": "ravi@123"
}
```
- **Response**:
```bash
{
  "message": "User Successfully Registered"
}
```
### 2. Login
- Endpoint: /login
- Method: POST
- Request Body:
```bash
{
  "email": "ravi@gmail.com",
  "password": "ravi@123"
}
```
- **Response**:
```bash
{
  "jwtToken": "<token>",
  "userId": "<user-id>"
}
```

## Transaction Endpoints
### 3. Create Transaction
- URL: /api/transactions
- Method: POST
- Headers: Authorization: Bearer <jwt-token>
- Request Body:
```bash
{
  "amount": 500,
  "transaction_type": "DEPOSIT",
  "user": "<user-id>"
}
```
- **Response**:
```bash
{
  "message": "Transaction successfully done"
}
```

### 4. Get User Transactions
- URL: /api/transactions/:id
- Method: GET
- Headers: Authorization: Bearer <jwt-token>
- **Response**:
```bash
{
  "transactions": [/* transactions array */]
}
```

### 5. Update Transaction Status
- URL: /api/transactions/:id
- Method: PUT
- Headers: Authorization: Bearer <jwt-token>
- Request Body:
```bash
{
  "status": "COMPLETED"
}
```
- **Response**:
```bash
{
  "message": "Transaction Status Updated Successfully"
}
```

### 6. Get Transaction by ID
- URL: /api/transaction/:id
- Method: GET
- Headers: Authorization: Bearer <jwt-token>
- **Response**:
```bash
{
  /* transaction details */
}
```


## Dependencies
- express: Fast, unopinionated web framework
- cors: Enable Cross-Origin Resource Sharing
- uuid: Generate unique identifiers
- mongodb: MongoDB driver for Node.js
- jsonwebtoken: Authenticate and secure API
- bcrypt: Hash passwords for secure storage
- dotenv: Manage environment variables
