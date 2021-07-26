Welcome to the employeeCourseHeroku wiki!

# employeeCourse repository
JPA @Entity Employee and Images uploading/downloading
- Spring Boot JPA @RestController without View and Thymeleaf
- Rest Controller with image `public class EmployeeImageController` and Swagger
- Application.properties
- Classes: JPA @Entity Employee and CrudRepository Interface
- Database: H2 (local or in Memory) and ddl.auto **for data**
- MongoDB connection and db **for images**

## employeeCourse (java-EE spring)

`Project Tree init:`

| <a href="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000041.png"><img src="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000041.png" width="250"></a>  | <a href="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000040.png"><img src="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000040.png" width="250"></a>  | <a href="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000042.png"><img src="https://github.com/AlbertProfe/images/blob/main/cifospring2021/2021-07-MongoDB-000042.png" width="250"></a> |


### employeeCourse2: 

Deployed on `Heroku`: https://employeecourse.herokuapp.com/

screenshoots from app: https://github.com/AlbertProfe/images/tree/main/cifospring2021/mockup

`How layout works:`

<a href="https://github.com/AlbertProfe/images/blob/main/cifospring2021/layout/layout_0.png"><img src="https://github.com/AlbertProfe/images/blob/main/cifospring2021/layout/layout_0.png" width="500"></a>

`Employee JPA relationships:`

<a href="https://github.com/AlbertProfe/images/blob/main/cifospring2021/employeeCourse.png"><img src="https://github.com/AlbertProfe/images/blob/main/cifospring2021/employeeCourse.png" width="500"></a>


### employeeCourse3: 
   - Application.properties: mongoDB and H2
   - Layout and fragment
      - layout.html
      - layout_login.html
   - Java classes JPA
      - n:m TA as two @Entity and `1:n` `n:1` `1:n`
      - Employee <> Expense (@Entity H2) `1:n` bidirectional
      - Employee <> Holidays (@Entity H2) `1:n` unidirectional
      - Employee <> Enrollment <> Course <> Certificate (@Entity H2)  `n:m`
      - Employee <> EmployeeImage (@Document MongoDB) `1:1` birectional
  - Rest Controller (Employee and EmployeeImage)
  - CommandLineRunner
       - HomeController Fill in entities in H2 and assign them
       - Employee @entity
         - `setEmployeeImageId` with `employeeImageId` string id from mongodb with  *to-do*
  - Employee (Items detail)
      - Empployee Detail
        - Path (th:scr) to mognodb image from `getEmployeeImageId`  via rest controller *to-do*
      - Courses
        - Add couse to employee (insert date and status *to-do*)
        - Update status
      - Expenses
        - Create expense
        - Delete expense (afer deleting return to Expenses or crete new detail *to-do*)
        - Update expense
      - Holidays
        - Add holidays date
        - Delete  holidays dates
        - Create holidays (rejects to create an existing year)
      - Upload Image
         - Rest Controller via Postman
      - Add Image:
        - upload image option (EmployeImage to mongoDB)
        -  `1:1 - bidirectional`  (EmployeImage <> Employee)
  - Enrollments *to-do*
  - Courses and filters *to-do*
  - Thymeleaf pagination *to-do*
  - Thymeleaf validation *to-do*
  - Abstract class and inhrence with audit and DTO *to-do*
  - Java 8 and H2 in memory to `DEPLOY: upload to Heroku`
