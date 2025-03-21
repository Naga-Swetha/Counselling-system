# Counselling System Installation Guide

This guide will help you install the Counselling System using XAMPP on any device.

## Prerequisites

1. XAMPP installed on your system
2. PHP 7.4 or higher
3. MySQL 5.7 or higher
4. Web browser (Chrome, Firefox, etc.)

## Installation Steps

### 1. Set Up XAMPP

1. Download and install XAMPP from [https://www.apachefriends.org/](https://www.apachefriends.org/)
2. Start XAMPP Control Panel
3. Start Apache and MySQL services

### 2. Install the System

1. Navigate to your XAMPP installation directory:
   - Windows: `C:\xampp\htdocs\`
   - Linux: `/opt/lampp/htdocs/`
   - macOS: `/Applications/XAMPP/htdocs/`

2. Create a new folder named `counselling-system`

3. Copy all system files into this folder

4. Open phpMyAdmin:
   - Go to `http://localhost/phpmyadmin`
   - Click on "New" to create a new database
   - Name it `counselling_system`
   - Click "Create"

5. Import the database schema:
   - Select the `counselling_system` database
   - Click on "Import" tab
   - Choose the `schema.sql` file from the system files
   - Click "Go" to import

### 3. Configure the System

1. Open `config/database.php` and verify the database connection settings:
   ```php
   $host = 'localhost';
   $dbname = 'counselling_system';
   $username = 'root';  // default XAMPP username
   $password = '';      // default XAMPP password
   ```

2. Create required directories and set permissions:
   - Create `uploads` directory in the root folder
   - Set write permissions for the `uploads` directory

### 4. Create Test Users

1. Open `http://localhost/counselling-system/create_test_principal.php` in your browser
   - This will create the principal account
   - Default credentials will be displayed on screen

2. Open `http://localhost/counselling-system/create_test_users.php` in your browser
   - This will create test accounts for all roles
   - Default credentials will be displayed on screen

### 5. Access the System

1. Open your web browser and go to:
   `http://localhost/counselling-system/`

2. Log in using any of the test accounts:
   - Principal
   - HOD
   - Mentor
   - Student

## Default Test Accounts

After running the test user creation scripts, you'll have these accounts:

1. Principal:
   - Username: `principal`
   - Password: `principal123`

2. HOD:
   - Username: `hod`
   - Password: `hod123`

3. Mentor:
   - Username: `mentor`
   - Password: `mentor123`

4. Student:
   - Username: `student_munna`
   - Password: `student123`

## Troubleshooting

1. If you see a database connection error:
   - Verify MySQL is running in XAMPP
   - Check database credentials in `config/database.php`
   - Ensure the database was created successfully

2. If you see a blank page:
   - Check PHP error logs in XAMPP
   - Enable error reporting in PHP
   - Verify all required files are present

3. If uploads don't work:
   - Check permissions on the `uploads` directory
   - Verify PHP upload settings in `php.ini`
