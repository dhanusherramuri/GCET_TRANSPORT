# GCET Transport Management System


This repository contains the source code for a web-based transport management system for Geethanjali College of Engineering and Technology (GCET). The system allows students to log in, apply for bus passes, and submit complaints regarding the transport services. It also includes separate Java utilities for parsing student data from an XML file.

## Features

*   **User Authentication**: Secure sign-up and login system for students.
*   **Session Management**: Maintains user sessions to provide a personalized experience.
*   **Bus Pass Application**: A form for students to apply for a bus pass, including name, roll number, address, and image upload functionality.
*   **Complaint System**: Users can submit complaints about bus services, specifying the complaint type and bus number.
*   **Dynamic Frontend**: Interactive user interface with responsive design elements.
*   **XML Data Parsing**: Includes Java programs that demonstrate DOM and SAX parsing of an XML file containing student details.

## Technologies Used

*   **Frontend**: HTML, CSS, JavaScript
*   **Backend**: PHP
*   **Database**: MySQL
*   **XML Parsing**: Java (DOM and SAX)

## Setup and Installation

To run this project locally, you will need a web server environment like XAMPP or WAMP.

1.  **Prerequisites**:
    *   A web server with PHP and MySQL (e.g., XAMPP).
    *   Java Development Kit (JDK) to run the XML parsing utilities.

2.  **Clone the repository**:
    ```sh
    git clone https://github.com/dhanusherramuri/GCET_TRANSPORT.git
    ```

3.  **Directory Setup**:
    *   Move the cloned repository folder into your web server's root directory (e.g., `htdocs` in XAMPP).

4.  **Database Configuration**:
    *   Start the Apache and MySQL services from your XAMPP/WAMP control panel.
    *   Open phpMyAdmin (`http://localhost/phpmyadmin`) and create a new database named `dt`.
    *   Execute the following SQL queries to create the necessary tables:

    ```sql
    -- Table for user registration
    CREATE TABLE `register` (
      `name` varchar(255) NOT NULL,
      `mid` varchar(255) NOT NULL,
      `pass` varchar(255) NOT NULL,
      PRIMARY KEY (`mid`)
    );

    -- Table for bus pass applications
    CREATE TABLE `bpd` (
      `nae` varchar(255) NOT NULL,
      `rno` varchar(50) NOT NULL,
      `addr` text NOT NULL,
      `fname` varchar(255) NOT NULL,
      `uploaded_on` datetime NOT NULL
    );

    -- Table for complaints
    CREATE TABLE `cb` (
      `complaints` text,
      `rt_no` varchar(10) DEFAULT NULL,
      `ct` varchar(255) DEFAULT NULL,
      `Uploaded_on` datetime DEFAULT NULL
    );
    ```

5.  **Access the Application**:
    *   Open your web browser and navigate to `http://localhost/GCET_TRANSPORT/dtproj.html` to access the login/signup page.

## File Usage

*   `dtproj.html`: The main entry point for users, featuring the login and sign-up forms.
*   `index.php`: The main dashboard displayed after a successful login.
*   `signup.php`: Handles the user registration logic.
*   `login.php`: Manages user login and session creation.
*   `logout.php`: Terminates the user session.
*   `bp.php`: Provides the bus pass application form and handles file uploads and data submission.
*   `complain.php`: The user interface for submitting complaints.
*   `cmp.php`: The backend script that processes and saves complaint data into the database.
*   `students.xml`: An XML file containing sample student data for the Java parsers.
*   `DOMParserDemo.java`: A Java program that parses `students.xml` using a DOM parser to find a student by ID.
*   `SAXParserxml.java`: A Java program that parses `students.xml` using a SAX parser to find a student by ID.
*   `1.css`, `v.css`: CSS files for styling the web application.

## XML Parsing Utilities (Java)

The repository includes two Java files for parsing `students.xml`. These are standalone command-line utilities.

### How to Run

1.  Make sure you have a JDK installed and configured.
2.  Place `DOMParserDemo.java`, `SAXParserxml.java`, and `students.xml` in the same directory.
3.  Open a terminal or command prompt in that directory.

#### DOM Parser

*   **Compile**:
    ```sh
    javac DOMParserDemo.java
    ```
*   **Run**:
    ```sh
    java DOMParserDemo
    ```
    The program will then prompt you to enter a student ID.

#### SAX Parser

*   **Compile**:
    ```sh
    javac SAXParserxml.java
    ```
*   **Run**:
    ```sh
    java SAXParserxml
    ```
    The program will prompt you to enter a student ID.
