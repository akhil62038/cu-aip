LIBRARY BOOK MANAGER — NETBEANS SETUP
=====================================

Technology:
- Java 17
- Apache NetBeans (Maven support)
- Apache Tomcat 10.1.x
- MySQL 8.x
- JSP, Jakarta Servlet 6.0 and JDBC

IMPORTANT VERSION NOTE:
This project uses Jakarta Servlet 6.0, so use Tomcat 10.1.x. Tomcat 11 uses
Servlet 6.1. The report's combination of Servlet 6.0 and Tomcat 11 is a
version mismatch; this project keeps Servlet 6.0 and uses compatible Tomcat 10.1.

1. Install Java 17 (JDK), Apache NetBeans, Apache Tomcat 10.1, and MySQL Server.
2. Extract the ZIP file.
3. Open NetBeans -> File -> Open Project.
4. Select the extracted LibraryBookManager folder (the folder containing pom.xml).
5. Wait for Maven dependencies to download.
6. In MySQL Workbench, open database/schema.sql and execute the complete script.
7. Configure the database connection before running:
   Windows Command Prompt:
     set BOOKTRACKER_DB_URL=jdbc:mysql://localhost:3306/book_issue_tracker
     set BOOKTRACKER_DB_USER=root
     set BOOKTRACKER_DB_PASSWORD=YOUR_MYSQL_PASSWORD
   Then start NetBeans from that same Command Prompt.
   Alternatively, edit DBUtil.java and set your local URL/user/password
   (not recommended for a shared/public project).
8. In NetBeans, right-click Servers -> Add Server -> Apache Tomcat.
   Select your Tomcat 10.1 installation and provide its manager credentials if asked.
9. Right-click the project -> Clean and Build.
10. Right-click the project -> Run. If the browser does not open automatically, visit:
      http://localhost:8080/LibraryBookManager/dashboard

FUNCTIONS:
- Add books
- Register borrowers
- Issue a book for 14 days
- Return an issued book
- View inventory, borrowers and issue history

TROUBLESHOOTING:
- "Access denied": check MySQL username/password and environment variables.
- "Unknown database": execute database/schema.sql.
- "Communications link failure": make sure MySQL Server is running.
- "404": confirm the context path is /LibraryBookManager and use /dashboard.
- Java version error: configure NetBeans and Tomcat to use JDK 17.
