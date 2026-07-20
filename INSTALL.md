# Installation Guide

## Overview

This guide explains how to install and run Budglet on a local machine.

## Prerequisites

Before installing Budglet, ensure the following software is installed:

- Java Development Kit (JDK) 22 or later
- PostgreSQL
- Maven (if building from source)
- JavaFX SDK (if running from an IDE)

## Project Setup

### 1. Clone the repository

```bash
git clone <repository-url>
cd BudgletProject
```

### 2. Create the PostgreSQL database

```bash
createdb -U postgres budglet
```

### 3. Import the database schema

```bash
psql -U postgres -d budglet -f schema.sql
```

### 4. Configure environment variables

Create or edit the `.env` file in the project root.

Example:

```text
DB_URL=jdbc:postgresql://localhost:5432/budglet
DB_USER=postgres
DB_PASSWORD=your_password_here
```

## Running the Application

### Option 1 - Windows Executable

Run:

```
dist/Budglet/Budglet.exe
```

### Option 2 - Java JAR

```bash
java -jar target/Budglet-1.0-all.jar
```

### Option 3 - IntelliJ IDEA

If running the project from IntelliJ, configure the required JavaFX VM options before launching the application.

## Default Test Account

When Budglet launches, the application seeds the database with sample data.

Before credentials:

Email:

```
budgeteer@budgeteer.budget
```

Password:

```
password
```

## Troubleshooting

### Database connection failed

-Verify PostgreSQL is running. 
-Verify the `.env` file contains the correct database credentials.
-Ensure the `budglet` database has been created. 

### JavaFX errors

If JavaFX modules cannot be found, verify that the JavaFX SDK is installed and correctly configured in your IDE.

### Application will not launch

- Verify JDK 22 or later is installed.
- Confirm the database schema has been imported successfully.
- Verify the `.env` configuration. 
