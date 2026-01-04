# User Certifications Portal

A comprehensive Spring Boot web application for managing user certifications, built with Java 21, Spring Boot 3.3.3, MySQL, and Thymeleaf. This platform allows users to browse certifications, request new ones, manage their profiles, and track their certification progress. Administrators can manage certifications and user certifications through a dedicated admin panel.

## 🚀 Features

### User Features
- **User Registration & Authentication**: Secure user registration and login system with Spring Security
- **Certification Catalogue**: Browse and search through available certifications
- **Profile Management**: View and update personal information, completed certifications, and flagged certifications
- **Certification Requests**: Request new certifications to be added to the platform
- **Certification Flagging**: Flag certifications of interest for future reference
- **Certification Details**: View detailed information about each certification including exam board, skills, learning time, and links

### Admin Features
- **Add Certifications**: Administrators can add new certifications to the platform
- **Manage User Certifications**: Assign certifications to users with date obtained and expiry dates
- **Admin Dashboard**: Access to administrative functions through role-based access control

### Technical Features
- **Spring Security**: Robust authentication and authorization with role-based access control (RBAC)
- **MySQL Database**: Persistent data storage with JPA/Hibernate
- **Responsive UI**: Modern, responsive interface built with Bootstrap 5
- **Session Management**: Secure session handling with single session per user
- **Password Encryption**: BCrypt password encoding for secure password storage

## 🛠️ Technology Stack

- **Backend**: 
  - Java 21
  - Spring Boot 3.3.3
  - Spring Security 6
  - Spring Data JPA
  - Spring Mail (for email functionality)
- **Frontend**: 
  - Thymeleaf (Server-side templating)
  - Bootstrap 5
  - HTML/CSS/JavaScript
- **Database**: 
  - MySQL 8.0+
- **Build Tool**: 
  - Maven
- **Other**: 
  - Lombok (for reducing boilerplate code)
  - OAuth2 Client (for future OAuth integration)

## 📋 Prerequisites

Before running this application, ensure you have the following installed:

- **Java 21** or higher
- **Maven 3.6+**
- **MySQL 8.0+** 
- **IDE** (IntelliJ IDEA, Eclipse, or VS Code recommended)

## 🔧 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/engr-muhammad-mansoor/certifications_manager.git
cd certifications_manager
```

### 2. Database Setup

Create a MySQL database:

```sql
CREATE DATABASE certification_db;
```

### 3. Configure Application Properties

Update the `src/main/resources/application.properties` file with your database credentials:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/certification_db
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```

**Note**: The application uses `ddl-auto=update`, which will automatically create/update the database schema on startup.

### 4. Build the Project

```bash
mvn clean install
```

### 5. Run the Application

```bash
mvn spring-boot:run
```

Or run the `UserCertificationsApplication.java` class directly from your IDE.

The application will be available at: `http://localhost:8080`

## 👤 Default Admin Credentials

The application automatically creates an admin user on first startup:

- **Email**: `admin@gmail.com`
- **Password**: `change_me_in_production`

**⚠️ Important**: Change the default admin password immediately after first login in a production environment!

## 📁 Project Structure

```
certifications/
├── src/
│   ├── main/
│   │   ├── java/com/user/certifications/
│   │   │   ├── config/              # Configuration classes (Security, Data Initialization)
│   │   │   ├── controllers/         # REST controllers for handling requests
│   │   │   ├── entities/            # JPA entity classes
│   │   │   ├── repositories/        # Spring Data JPA repositories
│   │   │   ├── servicesImp/         # Service implementation classes
│   │   │   └── UserCertificationsApplication.java
│   │   └── resources/
│   │       ├── static/              # Static resources (CSS, JS)
│   │       ├── templates/           # Thymeleaf templates
│   │       └── application.properties
│   └── test/                        # Test files
├── pom.xml                          # Maven configuration
└── README.md
```

## 🗄️ Database Schema

The application uses the following main entities:

- **users**: User accounts with roles (USER/ADMIN)
- **certifications**: Available certifications in the system
- **user_certifications**: User's completed certifications
- **user_flagged_certifications**: Certifications flagged by users
- **requested_certifications**: Certification requests from users

## 🔐 Security Features

- **Password Encryption**: All passwords are encrypted using BCrypt
- **Role-Based Access Control**: Different access levels for users and admins
- **Session Management**: Single session per user with automatic expiration
- **Secure Authentication**: Spring Security form-based authentication
- **CSRF Protection**: Enabled by default in Spring Security

## 📝 API Endpoints

### Public Endpoints
- `GET /login` - Login page
- `GET /register` - Registration page
- `POST /register` - User registration

### User Endpoints (Authenticated)
- `GET /home` - Home page with latest certifications
- `GET /catalogue` - Browse all certifications
- `GET /catalogue/search` - Search certifications
- `GET /certification/{id}` - View certification details
- `POST /certification/{id}/flag` - Flag a certification
- `GET /profile` - User profile page
- `POST /update` - Update user profile
- `GET /request` - Request certification page
- `POST /request` - Submit certification request

### Admin Endpoints (ADMIN role required)
- `GET /admin/add-certification` - Add certification form
- `POST /admin/add-certification` - Submit new certification
- `GET /admin/add-user-certification` - Assign certification to user
- `POST /admin/add-user-certification` - Submit user certification assignment

## 🎨 UI/UX Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern Bootstrap UI**: Clean and professional interface
- **Intuitive Navigation**: Easy-to-use navigation menu
- **Card-based Layout**: Certifications displayed in an organized card layout
- **Search Functionality**: Quick search across certifications

## 🔄 Future Enhancements

- Email notification system for certification updates
- OAuth2 social login integration
- Certification expiration reminders
- Advanced filtering and sorting options
- Export certification records (PDF/CSV)
- RESTful API for mobile applications
- Multi-language support
- Certification recommendations based on user profile

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Engr. M. Mansoor**

- GitHub: [@engr-muhammad-mansoor](https://github.com/engr-muhammad-mansoor)

## 🙏 Acknowledgments

- Spring Boot community
- Bootstrap team for the amazing UI framework
- All contributors and users of this project

## 📞 Support

If you have any questions or issues, please open an issue on the GitHub repository.

---

⭐ If you find this project helpful, please consider giving it a star!

