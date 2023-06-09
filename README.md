# Cinema-app
This project is a web application for a cinema. It includes functionality that allows users  registration, authentication and authorization to order tickets for movies, view the schedule of sessions, and information, descriptions about the films. 
In this program, the user can have two roles: ADMIN or USER.

The application is developed based on a 3-tier architecture:

- Data access layer (DAO);
- Application layer (service);
- Presentation layer (controllers);

# Features
- registration/authentication/authorization;
- create movies;
- create/update/remove movie sessions;
- create cinema halls;
- display list of all movies/movie sessions/cinema halls;
- creating shopping cart;
- add tickets to shopping cart;
- complete an order;
 
# Project structure
- `controllers:`
  -  Authentication - POST: /register (you can register, ALL)
  -  CinemaHall:
     - POST: /cinema-halls (add new cinema hall, role: ADMIN)
     - GET: /cinema-halls (display all the cinema halls, role: ADMIN, USER)
  - Movie:
     - POST: /movies (add new movie, role: ADMIN)
     - GET: /movies (display all the movies, role: ADMIN, USER)
  - MovieSession:
     - POST: /movie-sessions (add new movie session, role: ADMIN)
     - PUT: /movie-sessions/{id} (update movie session with specified id, role: ADMIN)
     - DELETE: /movie-sessions/{id} (delete movie session by id, role: ADMIN)
     - GET: /movie-sessions/available (display all the available movie sessions, role: ADMIN, USER)
  - Order:
     - GET: /orders (display all the orders, role: USER)
     - POST: /orders/complete (complete the current order, role: USER)
  - ShoppingCart:
     - GET: /shopping-carts/by-user (display the contents of the current user's shopping, role: USER)
     - PUT: /shopping-carts/movie-sessions (add movie session to the shopping cart, role: USER)
  - User - GET: /users/by-email (find user by email, role: ADMIN)
- `dao`: interfaces and their implementations are responsible for connection with the database and performing 
CRUD operations.
- `dto`: to transfer data between different layers or components of an application.
- `model`: stores information about entities and their properties.
- `security`: defines access rights to user according to user's role.
- `service`: interfaces and their implementations are responsible for the business logic of the application.
- `resources`: configuration file.

# Technologies
- Java `17.0.6`
- MySQL `8.0.32`
- Hibernate ORM `5.6.14`
- Spring Framework `5.3.20`
- Spring Security `5.6.10`
- Apache Tomcat `9.0.50`
- Maven `3.8.7`
- Maven Checkstyle Plugin `3.1.1`

# How to run
1. Configure Apache Tomcat for your IDE.
2. Install MySQL and MySQL Workbench.
3. Create  schema in your DB.
4. Clone this remote repository to your local repository .
5. In the resources/db.properties change YOUR_DRIVER, YOUR_URL, YOUR_USERNAME and YOUR_PASSWORD values to the ones you 
specified when installing MySQL, also change JDBC_DRIVER.
6. Run the application.
7. You can test app with credentials of this admin : admin - [admin@gmail.com](mailto:admin@gmail.com), password - `4321`
and user - [user@gmail.com](mailto:user@gmail.com), password - `1234`.
These users are already injected into our app. 
8. You can use Postman to send requests to my app.

# Author
Nadiia Huryk

[My LinkedIn](https://www.linkedin.com/in/nadiia-huryk-5241b0275/)