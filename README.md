# Database Management System Project

This project demonstrates the creation and management of a database system designed to store and process data related to companies, employees, clients, products, and projects. The implementation includes database schemas, sample data, triggers, views, and user roles.

## Features

### 1. Database Creation
- **Database Name**: `andrzejczak_filip`
- Character set: `utf8mb4`
- Collation: `utf8mb4_polish_ci`

### 2. Tables and Relationships
- **Tables**:
  - `firma`: Stores company details.
  - `klienci`: Contains client information.
  - `pracownicy`: Records employee details.
  - `projekty`: Holds project data.
  - `produkty`: Lists products with their prices.
  - `zlecenia`: Logs client orders.
  - `pracownicy_projekty`: Associates employees with projects.
  - `zlecenia_produkty`: Links orders with products.
- **Primary and Foreign Keys**:
  - Proper keys are used to establish relationships between tables, ensuring referential integrity.

### 3. Stored Functions and Triggers
- **Function**: `SprawdzDaty`
  - Ensures the end date of a project is not earlier than its start date.
- **Trigger**: `przed_zmiana_projektu`
  - Prevents invalid date updates in the `projekty` table.

### 4. Views
- **View**: `widok_projekty`
  - Provides a simplified view of project IDs and names.

### 5. User Management
- Created users with varying permissions:
  - `mafiaboss`: Full access.
  - `manager`: Limited access (SELECT, INSERT, UPDATE).
  - `peasant`: Read-only access to the `zlecenia` table.

### 6. Sample Data
- Preloaded tables with sample data for testing and demonstration purposes.

### 7. Miscellaneous Features
- Added constraints to ensure data integrity.
- Demonstrated data updates and deletion.

## Usage

### Prerequisites
- **MySQL** or compatible database system installed.
- Proper permissions to create databases and users.

### Steps
1. Import the SQL file into your database:
   ```bash
   mysql -u <username> -p < database_name < Filip_Andrzejczak-realizacja.txt
   ```
2. Access the database:
   ```sql
   USE andrzejczak_filip;
   ```
3. Explore tables, views, and sample data:
   ```sql
   SELECT * FROM widok_projekty;
   ```

### User Role Access
- Login with appropriate credentials to test role-based access.

## Example Queries
1. **View all employees in a specific company**:
   ```sql
   SELECT * FROM pracownicy WHERE firma_id = 1;
   ```
2. **Check project details**:
   ```sql
   SELECT * FROM projekty;
   ```
3. **View orders with associated products**:
   ```sql
   SELECT * FROM zlecenia_produkty;
   ```

## License
This project is licensed under the MIT License.
