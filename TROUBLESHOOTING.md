# Troubleshooting Guide

## Overview

This guide provides solutions to common issues that may occur while installing, configuring, or running Budglet. Most problems are related to Java installation, PostgreSQL configuration, environment variables, or JavaFX runtime settings.

Before troubleshooting, verify that your system meets all installation requirements described in the Installation Guide.

---

# Table of Contents

- Common Installation Issues
- Database Problems
- Environment Variable Issues
- JavaFX Runtime Errors
- Build Issues
- Application Startup Problems
- Login Problems
- Frequently Asked Questions
- Related Documentation

---

# Common Installation Issues

## Application Will Not Start

### Possible Causes

- Java is not installed
- Unsupported Java version
- Missing JavaFX runtime
- PostgreSQL service is not running

### Solution

Verify that the following software is installed:

- JDK 22 or newer
- PostgreSQL
- JavaFX SDK
- Maven (if building from source)

Restart the application after confirming all dependencies have been installed.

---

## Missing Database

### Problem

The application cannot connect to the Budglet database.

### Solution

Create the database:

```bash
createdb -U postgres budglet
```

Then load the schema:

```bash
psql -U postgres -d budglet -f schema.sql
```

---

# Database Problems

## Connection Refused

### Cause

The PostgreSQL server is not running.

### Solution

Start the PostgreSQL service and verify that it is listening on the default port (5432).

---

## Authentication Failed

### Cause

Incorrect database username or password.

### Solution

Verify the values inside the `.env` file.

Example:

```env
DB_URL=jdbc:postgresql://localhost:5432/budglet
DB_USER=postgres
DB_PASSWORD=your_password
```

---

## Schema Not Found

### Cause

The database exists but the schema has not been imported.

### Solution

Run:

```bash
psql -U postgres -d budglet -f schema.sql
```

---

# Environment Variable Issues

If Budglet cannot locate the database, verify that the project root contains a valid `.env` file.

Required variables:

```env
DB_URL=
DB_USER=
DB_PASSWORD=
```

Restart the application after making changes.

---

# JavaFX Runtime Errors

## JavaFX Components Not Found

If running from IntelliJ or from the JAR file, ensure that the required JavaFX VM options have been configured correctly.

Example:

```
--module-path <javafx-sdk>/lib
--add-modules javafx.controls,javafx.fxml
```

Refer to the Installation Guide for the complete VM configuration.

---

# Build Issues

## Maven Build Fails

Possible causes include:

- Missing JavaFX SDK
- Unsupported JDK version
- Missing dependencies
- Incorrect project configuration

Recommended steps:

1. Verify Java version.
2. Refresh Maven dependencies.
3. Rebuild the project.
4. Restart IntelliJ.

---

# Application Startup Problems

## Blank Window

Possible causes:

- Database connection failure
- JavaFX initialization error
- Missing configuration files

Verify:

- PostgreSQL is running.
- `.env` file exists.
- Database schema has been imported.

---

## Application Closes Immediately

Possible causes:

- Missing JavaFX runtime
- Incorrect VM options
- Unsupported Java version

Verify all installation requirements before launching the application.

---

# Login Problems

## Unable to Sign In

Possible causes:

- Incorrect email
- Incorrect password
- Database connection failure

For testing, the application includes mock user credentials:

Email:

```
budgeteer@budgeteer.budget
```

Password:

```
password
```

If these credentials do not work, verify that the database was seeded successfully during application startup.

---

# Frequently Asked Questions

## Which Java version is required?

JDK 22 or newer.

---

## Which database is supported?

PostgreSQL.

---

## Can the application run without PostgreSQL?

No.

Budglet stores all user information, transactions, budgets, and financial records within a PostgreSQL database.

---

## Why won't the executable launch?

Verify that:

- Java is installed.
- PostgreSQL is running.
- The database has been created.
- The schema has been imported.
- The `.env` file has been configured correctly.

---

# Related Documentation

- README.md
- INSTALL.md
- USER_GUIDE.md
- ARCHITECTURE.md
- SYSTEM_DESIGN.md
- DATABASE.md
- TESTING.md