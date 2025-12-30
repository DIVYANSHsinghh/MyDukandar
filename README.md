# MyDukandar - Multi-Role Store Rating Platform

A comprehensive full-stack web application for rating and reviewing stores, built with React and Node.js. MyDukandar enables users to discover, rate, and review local stores while providing store owners and administrators with powerful management tools.

## 🌟 Features

### For Users
- **Browse Stores**: Discover and search for local stores
- **Rate & Review**: Submit star ratings and reviews for stores
- **Store Details**: View comprehensive store information and ratings
- **User Dashboard**: Access personalized dashboard with browsing history

### For Store Owners
- **Store Management**: Manage your stores and view detailed analytics
- **Rating Analytics**: Track ratings and reviews for your stores
- **Customer Insights**: View who rated your stores and their feedback
- **Owner Dashboard**: Centralized dashboard for all your business metrics

### For Administrators
- **Platform Management**: Complete control over stores and users
- **Store Administration**: Create, update, and delete stores
- **User Management**: Create users and assign store ownership
- **Store Assignment**: Assign stores to store owners
- **Admin Dashboard**: Overview of platform statistics and management tools

## 🚀 Tech Stack

### Frontend
- **React 19.2.0** - Modern UI library
- **Vite 7.2.2** - Fast build tool and dev server
- **React Router DOM 7.9.6** - Client-side routing
- **Axios 1.13.2** - HTTP client for API calls
- **Tailwind CSS 3.4.18** - Utility-first CSS framework

### Backend
- **Node.js** - Runtime environment
- **Express 5.1.0** - Web framework
- **PostgreSQL** - Relational database
- **Sequelize 6.37.7** - ORM for database operations
- **JWT (jsonwebtoken 9.0.2)** - Authentication and authorization
- **bcryptjs 3.0.3** - Password hashing
- **Joi 18.0.1** - Input validation
- **CORS 2.8.5** - Cross-origin resource sharing

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **PostgreSQL** (v12 or higher)
- **Git**

## 🔧 Installation

### 1. Clone the repository
```bash
git clone <repository-url>
cd Review-Platform
```

### 2. Backend Setup

```bash
cd Backend
npm install
```

Create a `.env` file in the `Backend` directory:
```env
PORT=4000
DB_HOST=localhost
DB_PORT=5432
DB_NAME=rating_db
DB_USER=postgres
DB_PASS=your_postgres_password

JWT_SECRET=your_jwt_secret_key
JWT_EXPIRES_IN=7d
BCRYPT_SALT_ROUNDS=10
```

### 3. Database Setup

Create the PostgreSQL database:
```sql
CREATE DATABASE rating_db;
```

The application will automatically create tables using Sequelize sync when you start the server.

### 4. Frontend Setup

```bash
cd Frontend
npm install
```

## 🏃 Running the Application

### Start Backend Server

```bash
cd Backend
npm run dev
```

The backend server will start on `http://localhost:4000`

### Start Frontend Server

In a new terminal:
```bash
cd Frontend
npm run dev
```

The frontend application will start on `http://localhost:3000`

## 📁 Project Structure

```
Review-Platform/
├── Backend/
│   ├── src/
│   │   ├── config/          # Database and app configuration
│   │   ├── controllers/     # Request handlers
│   │   ├── middleware/      # Auth and role middleware
│   │   ├── models/          # Sequelize models
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic services
│   │   ├── utils/           # Utility functions
│   │   ├── migrations/      # Database migrations
│   │   ├── seeders/         # Database seeders
│   │   ├── app.js           # Express app setup
│   │   └── server.js        # Server entry point
│   └── package.json
│
└── Frontend/
    ├── src/
    │   ├── components/      # Reusable React components
    │   ├── context/         # React context providers
    │   ├── pages/           # Page components
    │   ├── services/        # API service layer
    │   ├── App.jsx          # Main app component
    │   └── main.jsx         # Entry point
    └── package.json
```

## 🔐 Authentication & Authorization

The application uses JWT (JSON Web Tokens) for authentication with three distinct user roles:

- **User (normal)**: Can browse and rate stores
- **Store Owner (store_owner)**: Can manage their stores and view ratings
- **Admin**: Full platform access and management capabilities

Protected routes are enforced using middleware that validates JWT tokens and user roles.

## 🛠️ API Endpoints

### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `PUT /api/auth/update` - Update password

### Stores
- `GET /api/stores` - List all stores
- `GET /api/stores/search` - Search stores
- `GET /api/stores/:id` - Get store details

### Ratings
- `POST /api/ratings/:storeId` - Submit rating

### Owner
- `GET /api/owner/stores` - Get owner's stores
- `GET /api/owner/stores/:storeId/raters` - Get store raters
- `GET /api/owner/stores/:storeId/avg` - Get average rating

### Admin
- `GET /api/admin/stores` - Get all stores
- `POST /api/admin/stores` - Create store
- `PUT /api/admin/stores/:id` - Update store
- `DELETE /api/admin/stores/:id` - Delete store
- `GET /api/admin/users` - Search users
- `POST /api/admin/users` - Create user

## 🎨 UI/UX Features

- Modern, responsive design with Tailwind CSS
- Intuitive navigation and user interface
- Real-time toast notifications for user feedback
- Star rating component for easy store rating
- Protected routes based on user roles
- Loading states and error handling

## 📝 Database Schema

The application uses the following main models:
- **Users**: User accounts with roles (user, store_owner, admin)
- **Stores**: Store information with name, address, and owner
- **Ratings**: User ratings linked to stores

## 🔒 Security Features

- Password hashing with bcryptjs
- JWT-based authentication
- Role-based access control (RBAC)
- Input validation with Joi
- CORS configuration
- Protected API routes

## 📚 Additional Documentation

- [Database Setup Guide](./Backend/DATABASE_SETUP.md) - Detailed PostgreSQL setup instructions

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [ISC License](https://opensource.org/licenses/ISC).

## 👨‍💻 Author

Built with ❤️ using React and Node.js

---

**Note**: Make sure PostgreSQL is running before starting the backend server. Refer to `Backend/DATABASE_SETUP.md` for detailed database setup instructions.


