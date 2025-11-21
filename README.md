# Nimap API Testing - Postman Machine Test

## 📋 Project Overview
This project contains Postman API testing collection for Nimap Infotech's machine test. It demonstrates API testing capabilities including authentication, request/response validation, and automated testing.

## 🔗 Application Under Test
- **URL**: https://testffc.nimapinfotech.com
- **Test Credentials**:
  - User ID: `9519519519`
  - Password: `12345678`

## 🎯 Test Scenarios Covered

### 1. Authentication Testing
- ✅ Login with valid credentials
- ✅ Login with invalid credentials
- ✅ Token extraction and storage

### 2. Customer Management
- ✅ Add new customer 
- ✅ Retrieve customer data

## 🛠️ Setup Instructions

### Prerequisites
- Postman Desktop App or Postman Web
- Git (for cloning repository)

### Installation Steps

1. **Clone the Repository**
```bash
   git clone https://github.com/YOUR-USERNAME/nimap-api-testing-postman.git
   cd nimap-api-testing-postman
```

2. **Import Collection into Postman**
   - Open Postman
   - Click **Import** button
   - Select `Nimap_API_Testing_Collection.json`
   - Click **Import**

3. **Import Environment**
   - Click **Import** button
   - Select `Nimap_Test_Environment.json`
   - Click **Import**

4. **Select Environment**
   - From environment dropdown (top-right)
   - Select **Nimap Test Environment**

## 🚀 Running the Tests

### Option 1: Run Individual Requests
1. Execute **"Login - Valid Credentials"** first
2. Verify authentication token is saved
3. Run **"Add Customer"** request
4. Run **"Get Customers"** request

### Option 2: Run Entire Collection
1. Click on collection name
2. Click **Run** button
3. Select all requests
4. Click **Run Nimap API Testing**
5. View test results

## 📁 Project Structure
```
nimap-api-testing-postman/
│
├── Nimap_API_Testing_Collection.json    # Postman collection file
├── Nimap_Test_Environment.json          # Environment variables
├── README.md                             # Project documentation
├── screenshots/                          # Test execution screenshots
│   ├── valid-login.png
│   ├── invalid-login.png
│   ├── add-customer.png
│   └── collection-run.png
└── .gitignore
```

## 📊 API Endpoints Tested

### 1. Login API
- **Endpoint**: `/api/account/authenticate` 
- **Method**: POST
- **Headers**: Content-Type: application/json
- **Body**:
```json
  {
    "userId": "9519519519",
    "password": "12345678"
  }
```
- **Expected Response**: 200 OK with auth token

### 2. Add Customer API
- **Endpoint**: `/api/customer` (or actual endpoint)
- **Method**: POST
- **Headers**: 
  - Content-Type: application/json
  - Authorization: Bearer {token}
- **Body**:
```json
  {
    "name": "John Doe",
    "email": "johndoe@example.com",
    "mobile": "9876543210",
    "address": "123 Main Street, Mumbai"
  }
```
- **Expected Response**: 201 Created or 200 OK

## ✅ Test Validations

### Automated Tests Include:
- ✅ Status code verification
- ✅ Response time validation
- ✅ Response body structure validation
- ✅ Authentication token extraction
- ✅ Error message validation for invalid inputs
- ✅ Required fields validation

## 🔑 Environment Variables

| Variable | Description |
|----------|-------------|
| `baseURL` | Base URL of the application |
| `userId` | Valid user ID for login |
| `password` | Valid password for login |
| `authToken` | Authentication token (auto-populated) |
| `invalidUserId` | Invalid user ID for negative testing |
| `invalidPassword` | Invalid password for negative testing |


## 🎓 Key Learnings

1. **Environment Setup**: Created reusable environment with base URLs and variables
2. **Variable Management**: Used environment variables for credentials and tokens
3. **Authentication Flow**: Implemented Bearer token authentication
4. **Request Chaining**: Extracted and reused auth token across requests
5. **Test Automation**: Written automated tests for validation
6. **Error Handling**: Tested both success and failure scenarios

## 📝 Notes

- Authentication token is automatically extracted and stored after successful login
- Invalid login attempts are tested to ensure proper error handling
- All customer data in tests uses dummy/test data
- Tests are designed to be repeatable and maintainable


This project is created for educational and testing purposes as part of Nimap Infotech's machine test.

