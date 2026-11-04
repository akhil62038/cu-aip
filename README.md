# Library Book Manager — NetBeans Maven Web Application

## Requirements
- JDK 17
- Apache NetBeans with Maven support
- Apache Tomcat 11
- MySQL Server 8.x (and MySQL Workbench, optional)

## 1. Create the database
1. Start MySQL.
2. Open `database/schema.sql` in MySQL Workbench.
3. Execute the complete script.

## 2. Configure database credentials
Set the following environment variables before starting NetBeans/Tomcat:
- `BOOKTRACKER_DB_URL` = `jdbc:mysql://localhost:3306/book_issue_tracker?useSSL=false&serverTimezone=UTC`
- `BOOKTRACKER_DB_USER` = your MySQL username (commonly `root`)
- `BOOKTRACKER_DB_PASSWORD` = your MySQL password

Alternatively, edit `src/main/java/com/akhil/library/util/DBUtil.java` and set your local values. Do not upload real passwords to GitHub.

## 3. Open in NetBeans
1. Extract the ZIP file.
2. Open NetBeans.
3. Select **File → Open Project**.
4. Select the extracted `LibraryBookManager-NetBeans` folder (the folder containing `pom.xml`).
5. Wait for Maven dependencies to download.
6. Add Tomcat 11: **Tools → Servers → Add Server → Apache Tomcat**.
7. Right-click the project → **Properties → Run** and select Tomcat 11.
8. Right-click the project → **Run**.

Open:
`http://localhost:8080/LibraryBookManager/dashboard`

## 4. Test the application
1. Add a book with a title, author, ISBN and number of copies.
2. Register a borrower.
3. Issue a book to that borrower.
4. Confirm that available copies decrease.
5. Return the book and confirm that available copies increase.

## Notes
- This project uses `jakarta.servlet` and requires Tomcat 11 (not Tomcat 9).
- The application is a classroom/demo project. It does not include login or role-based access control.
- The database password is read from environment variables. Set it before launching the server.
