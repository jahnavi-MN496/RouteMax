# RouteMax �

An end-to-end Parcel Management System built with Spring Boot, MySQL, and React. It enables users to track parcels and administrators to manage deliveries and users efficiently.

##  Features

###  Authentication & Authorization
- **User Signup & Login** with role-based redirection:
  - Users → redirected to the User Dashboard
  - Admins → redirected to the Admin Dashboard

###  Parcel Management

**Admin Capabilities:**
- Create, update, and delete parcels
- Manage delivery status
- Add, update, and delete user information
- Generate a unique parcel token for each new parcel

**User Capabilities:**
- Receive parcel token via email when parcel is created/updated
- Enter the token to track parcel status
- View history of previous parcels

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Backend** | Spring Boot (REST APIs) |
| **Database** | MySQL |
| **Frontend** | React.js |
| **Authentication** | Spring Security & JWT |
| **Email Service** | JavaMailSender |

##  Project Structure

```
RouteMax/
│
├── backend/                # Spring Boot backend
│   ├── src/
│   │   └── main/
│   │       ├── java/       # Java source files
│   │       └── resources/  # Application properties, templates
│   └── pom.xml             # Maven dependencies
│
├── frontend/               # React frontend
│   ├── public/             # Public assets
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Application pages
│   │   └── services/       # API services
│   └── package.json        # npm dependencies
│
└── README.md               # Project documentation
```

##  Installation & Setup

### Prerequisites
- Java 17+ (JDK)
- Node.js 16+ & npm
- MySQL 8.0+
- Maven 3.6+

### 1️⃣ Clone the repository

```bash
git clone https://github.com/jahnavi-MN496/RouteMax.git
cd RouteMax
```

### 2️⃣ Backend Setup (Spring Boot + MySQL)

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create a MySQL database:
   ```sql
   CREATE DATABASE routemax;
   ```

3. Configure `src/main/resources/application.properties`:
   ```properties
   # Database Configuration
   spring.datasource.url=jdbc:mysql://localhost:3306/routemax
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true

   # JWT Configuration
   jwt.secret=your_secret_key
   jwt.expiration=86400000

   # Email Configuration
   spring.mail.host=smtp.gmail.com
   spring.mail.port=587
   spring.mail.username=your_email@gmail.com
   spring.mail.password=your_app_password
   spring.mail.properties.mail.smtp.auth=true
   spring.mail.properties.mail.smtp.starttls.enable=true
   ```

4. Run the Spring Boot application:
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

   The backend server will start at `http://localhost:8080`

### 3️⃣ Frontend Setup (React)

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure API endpoint in `src/config.js` (if needed):
   ```javascript
   export const API_BASE_URL = 'http://localhost:8080/api';
   ```

4. Run the React app:
   ```bash
   npm start
   ```

   The frontend will start at `http://localhost:3000`

##  Usage

### User Flow
1. **Sign up** or **Login** with your credentials
2. **Receive token** via email when a parcel is assigned
3. **Track parcel** by entering the token
4. **View history** of all your previous parcels

### Admin Flow
1. **Login** with admin credentials
2. **Manage parcels** - Create, update, delete parcels
3. **Manage users** - Add, update, delete user accounts
4. **Update delivery status** - Mark parcels as shipped, in-transit, delivered


##  Default Admin Credentials

```
Email: admin@routemax.com
Password: admin123
```

>  **Important:** Change default admin credentials after first login

##  API Endpoints

### Authentication
- `POST /api/auth/signup` - Register new user
- `POST /api/auth/login` - User login

### Parcels
- `GET /api/parcels` - Get all parcels (Admin)
- `POST /api/parcels` - Create new parcel (Admin)
- `PUT /api/parcels/{id}` - Update parcel (Admin)
- `DELETE /api/parcels/{id}` - Delete parcel (Admin)
- `GET /api/parcels/track/{token}` - Track parcel by token (User)

### Users
- `GET /api/users` - Get all users (Admin)
- `PUT /api/users/{id}` - Update user (Admin)
- `DELETE /api/users/{id}` - Delete user (Admin)

##  Future Enhancements

- [ ] Real-time delivery tracking with Google Maps integration
- [ ] SMS/Push notifications for delivery updates
- [ ] QR code generation for parcels
- [ ] Multi-language support
- [ ] Advanced analytics dashboard
- [ ] Delivery route optimization
- [ ] Mobile app (React Native)

##  Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

##  License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

##  Author

**Sahitha Chunduri**
- GitHub: [jahnavi-MN496](https://github.com/jahnavi-MN496)

##  Acknowledgments

- Spring Boot Documentation
- React Documentation
- MySQL Documentation

---

 If you found this project helpful, please give it a star!

##  Support

For support, email jahnavi@example.com or open an issue in the repository.
