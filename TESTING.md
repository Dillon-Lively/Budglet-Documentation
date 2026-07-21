# Testing Guide

## Overview

Testing was performed throughout the development of Budglet to verify that the application's core functionality operated correctly and consistently. The primary goals were to validate user authentication, registration, budgeting functionality, financial transactions, and database communication while ensuring a reliable user experience.

The Software Design Specification documents both automated unit tests included in the project's Maven build and additional functional test cases planned for future implementation.

---

# Table of Contents

- [Testing Strategy](#testing-strategy)
- [Testing Environment](#testing-environment)
- [Types of Testing](#types-of-testing)
- [Automated Unit Tests](#automated-unit-tests)
- [Planned Functional Tests](#planned-functional-tests)
- [Test Coverage](#test-coverage)
- [Known Limitations](#known-limitations)
- [Future Improvements](#future-improvements)
- [Related Documentation](#related-documentation)

---

# Testing Strategy

Budglet follows a layered software architecture consisting of:

- JavaFX User Interface
- Controller Layer
- Service Layer
- Data Access Objects (DAO)
- PostgreSQL Database

Testing focused on validating both individual features and complete user workflows, ensuring that information entered through the graphical interface was processed correctly and persisted within the database.

The project combines automated unit tests with additional manual and functional test cases documented in the Software Design Specification.

---

# Testing Environment

| Component | Technology |
|-----------|------------|
| Programming Language | Java |
| GUI Framework | JavaFX |
| Database | PostgreSQL |
| IDE | IntelliJ IDEA |
| Build Tool | Maven |
| Version Control | Git / GitHub |

Testing was performed using a local PostgreSQL database during application development.

---

# Types of Testing

The Software Design Specification identifies five categories of testing.

## Performance Testing

Performance testing evaluates whether common application operations complete within acceptable response times.

Examples include:

- Loading financial information
- Searching transaction history
- Retrieving budgeting information

---

## Accuracy Testing

Accuracy testing verifies that the application produces the expected output for a given input.

Examples include:

- User authentication
- Registration validation
- Database queries
- Financial calculations

Most implemented unit tests fall into this category.

---

## User Interface Testing

User interface testing evaluates the application's usability.

Testing verifies that users can:

- Navigate the application
- Complete forms
- Receive meaningful validation messages
- Successfully perform common tasks

---

## Security Testing

Security testing ensures that only authenticated users can access protected application functionality.

Examples include:

- Login validation
- Password verification
- Authentication failures

---

## Repeatability Testing

Repeatability testing confirms that identical inputs consistently produce identical outputs.

Examples include:

- Login attempts
- Registration validation
- Financial calculations
- Budget progress calculations

---

# Automated Unit Tests

The project includes six automated unit tests that are part of the Maven build.

| Feature | Test Scenario | Expected Result | Status |
|----------|---------------|-----------------|:------:|
| Login | Valid email with incorrect password | Authentication rejected | ✅ Passed |
| Login | Valid email with correct password | User successfully logs in | ✅ Passed |
| Login | Non-existent email | Authentication rejected | ✅ Passed |
| Registration | Valid new user information | Registration successful | ✅ Passed |
| Registration | Empty required fields | Validation message displayed | ✅ Passed |
| Registration | Existing email | Duplicate registration rejected | ✅ Passed |

These tests verify the application's authentication and registration logic while ensuring that invalid user input is handled correctly.

---

# Planned Functional Tests

In addition to the implemented unit tests, the Software Design Specification documents several functional test cases intended for future development.

## User Registration

- Register with valid information
- Register with an existing email
- Register with empty required fields

---

## User Authentication

- Successful login
- Incorrect password
- Non-existent account
- Empty login fields

---

## Financial Accounts

- Add external account
- Invalid account information
- Successful account creation

---

## Income and Expense Management

- Create recurring income
- Create recurring expenses
- Validate incorrect financial input

---

## Transactions

- Successful transaction
- Insufficient account balance
- Transaction persistence

---

## Budget Management

- Create savings goals
- Create spending limits
- Create cutdown budgets
- Monitor budget progress

---

## Financial Reporting

Future testing also includes validating reporting functionality and ensuring accurate visualization of financial information.

---

# Test Coverage

Testing primarily focused on validating the application's highest-priority functionality.

| Application Feature | Coverage |
|---------------------|:--------:|
| User Registration | ✅ |
| User Login | ✅ |
| Authentication Validation | ✅ |
| Form Validation | ✅ |
| Database Communication | ✅ |
| Budget Creation | Planned |
| Transaction Processing | Planned |
| Financial Reports | Planned |
| Performance | Planned |
| User Interface | Planned |
| Security | Planned |

---

# Known Limitations

Budglet was developed as part of a university Software Engineering course.

Testing primarily focused on validating core functionality rather than achieving production-level test coverage.

Current limitations include:

- Limited automated unit testing
- Manual verification for several workflows
- No automated JavaFX UI testing
- No performance benchmarking
- No penetration or security auditing
- No continuous integration pipeline

Despite these limitations, the implemented unit tests successfully verified the application's authentication and registration functionality while additional functional tests were documented for future development.

---

# Future Improvements

Future versions of Budglet could expand testing through:

- Additional JUnit unit tests
- DAO integration testing
- Automated JavaFX UI testing
- Continuous Integration (CI)
- Code coverage reporting
- Performance benchmarking
- Automated regression testing
- Security auditing

These improvements would increase confidence in application reliability while simplifying long-term maintenance.

---

# Related Documentation

- [README](README.md)
- [Installation Guide](INSTALL.md)
- [User Guide](USER_GUIDE.md)
- [Architecture](ARCHITECTURE.md)
- [System Design](SYSTEM_DESIGN.md)
- [Database Documentation](DATABASE.md)
- [Troubleshooting Guide](TROUBLESHOOTING.md)