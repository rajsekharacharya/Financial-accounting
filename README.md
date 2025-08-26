# Account Management Software

![Account Management Banner](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white) ![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white) ![REST API](https://img.shields.io/badge/REST%20API-000000?style=for-the-badge&logo=rest&logoColor=white) ![Accounting](https://img.shields.io/badge/Accounting-Software-blue?style=for-the-badge)

📊 **A robust, Spring Boot-based account management system designed for efficient handling of financial transactions, balance sheets, and auditing. Built with Java, this backend application provides RESTful APIs for managing particulars, transactions, dashboards, and more.**

## 📝 Project Overview

This project is the backend source code for the IOS TTPG Account Management Software. It focuses on core accounting functionalities such as transaction processing, balance sheet generation, fiscal year coding, OTP generation for security, and number-to-word conversion for Indian currency. The application uses Spring Boot for rapid development, JPA for data persistence, and Spring Security for auditing and authentication.

Key highlights:
- **Auditing Support**: Tracks created/updated records with user details and timestamps.
- **Currency Utilities**: Converts numbers to words (e.g., for cheques) in Indian Rupees format.
- **Fiscal Year Management**: Generates codes like "2024-25" based on input dates.
- **OTP Generation**: Secure random OTPs for authentication.
- **RESTful Endpoints**: CRUD operations for balance sheets, transactions, particulars, and more.

This software is ideal for small to medium-sized businesses needing a scalable accounting backend.

## ✨ Features

- 🚀 **Balance Sheet Management**: Create, update, delete, and query balance sheets by date, ID, or period. Includes monthly summaries and dashboard data.
- 💼 **Transaction Handling**: Post, update, and delete transactions with support for multiple entries.
- 📈 **Dashboard Insights**: Retrieve aggregated data for quick overviews.
- 🛡️ **Security & Auditing**: Automatic auditing of changes using Spring Security. OTP generation for secure operations.
- 💱 **Currency & Fiscal Tools**: Convert amounts to words (e.g., "One Hundred Rupees Only") and generate fiscal year codes.
- 👤 **User & Particulars Management**: Manage account particulars (ledger heads) and user-related operations.
- 📅 **In-Person Balance Sheets**: Specialized handling for in-person financial records.

## 🛠️ Technologies Used

- **Backend Framework**: Spring Boot  (with Auto-Configuration, JPA Auditing)
- **Language**: Java 17+
- **Database**: JPA/Hibernate (configurable for MySQL/PostgreSQL/etc.)
- **Security**: Spring Security for authentication and auditing
- **Utilities**: 
  - Number to Word Conversion (Indian Currency)
  - OTP Generator
  - Fiscal Year Code Generator
- **Dependencies**: Lombok for boilerplate reduction, Spring Data JPA, etc.
- **Build Tool**: Maven (assumed from typical Spring Boot setup)

## 📦 Installation & Setup

### Prerequisites
- Java JDK 17 or higher
- Maven 3.6+
- A relational database (e.g., MySQL, PostgreSQL)
- Git

### Steps
1. **Clone the Repository**:
   ```
   git clone https://github.com/rajsekharacharya/Financial-accounting.git
   ```

2. **Configure Application Properties**:
   - Edit `src/main/resources/application.properties` or `application.yml`:
     ```
     spring.datasource.url=jdbc:mysql://localhost:3306/yourdb
     spring.datasource.username=root
     spring.datasource.password=yourpassword
     spring.jpa.hibernate.ddl-auto=update
     ```

3. **Build the Project**:
   ```
   mvn clean install
   ```

4. **Run the Application**:
   ```
   mvn spring-boot:run
   ```
   - The app will start on `http://localhost:8080`.

5. **Database Setup**:
   - The app uses JPA to auto-create tables. Ensure your DB is running.

## 🖥️ Usage

Once running, access the REST APIs via tools like Postman or curl.

### Example API Calls

- **Get All Balance Sheets**:
  ```
  GET /api/balance-sheets
  ```

- **Create a Transaction**:
  ```
  POST /api/transactions
  Content-Type: application/json
  Body: [{"amount": 1000, "description": "Sample Transaction"}]
  ```

- **Generate OTP**:
  - Use the `OTPGenerator` utility class internally for secure operations.

- **Convert Number to Words**:
  - Integrated in services; e.g., `NumberToWordExample.convertToIndianCurrency("1000.50")` → "One Thousand And Fifty Paise Only".

For full API documentation, refer to the controllers in `src/main/java/com/app/account/controller/`.

## 📊 API Endpoints Overview

| Endpoint | Method | Description | Parameters |
|----------|--------|-------------|------------|
| `/api/balance-sheets` | GET | Get all balance sheets | - |
| `/api/balance-sheets/byId` | GET | Get balance sheet by ID | `id` (Integer) |
| `/api/balance-sheets/add` | POST | Create balance sheet | JSON Body |
| `/api/transactions` | POST | Create transactions | JSON Array Body |
| `/api/particulars` | GET | Get all particulars | - |
| `/dashboard/getDashboardData` | GET | Get dashboard data | - |
| `/api/in-person-balance-sheets` | GET | Get in-person balance sheets | - |

Explore the source code for more endpoints in controllers like `BalanceSheetController.java`, `TransactionController.java`, etc.

## 🤝 Contributing

Contributions are welcome! Follow these steps:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add YourFeature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

Please ensure code follows Java best practices and includes tests.

## 📄 License
Apache 2.0 - See [LICENSE](LICENSE) for details.

## 📧 Contact
- **Author**: Rajsekhar Acharya
- **Email**: rajsekhar.acharya@gmail.com (placeholder)
- **GitHub**: [https://github.com/rajsekharacharya/Financial-accounting](https://github.com/rajsekharacharya/Financial-accounting)

⭐ Star the repo if you find it useful!