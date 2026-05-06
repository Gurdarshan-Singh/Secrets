# 🔐 Secrets - Anonymous Secret Sharing Platform

A secure web application where users can register, authenticate, and share secrets anonymously. Built with Node.js, Express, MongoDB, and EJS templating.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Security Features](#security-features)
- [Responsive Design](#responsive-design)

## ✨ Features

- **User Registration**: Create a new account with email and password
- **User Login**: Securely authenticate existing users
- **Password Encryption**: All passwords are encrypted using mongoose-encryption plugin
- **Anonymous Secrets**: Share secrets securely after authentication
- **Responsive UI**: Mobile-friendly interface that works on all devices
- **Modern Bootstrap Design**: Clean and intuitive user interface

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Backend** | Node.js + Express.js |
| **Database** | MongoDB |
| **Templating** | EJS (Embedded JavaScript) |
| **Styling** | Bootstrap 4.2.1 + Custom CSS |
| **Encryption** | mongoose-encryption |
| **Icons** | Font Awesome 5.6.3 |
| **Middleware** | body-parser |
| **Environment** | dotenv |

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v12 or higher)
- **npm** (comes with Node.js)
- **MongoDB** (running locally on port 27017 or provide connection string)

## 🚀 Installation

1. **Clone or download the project**
   ```bash
   cd Secrets
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create a `.env` file** in the root directory
   ```bash
   touch .env
   ```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory with the following content:

```env
SECRET=your_very_secure_secret_key_here
```

**Important**: 
- Replace `your_very_secure_secret_key_here` with a strong, random secret key
- This secret is used to encrypt passwords in the database
- Never commit `.env` to version control
- Use a strong password or passphrase (at least 32 characters recommended)

### MongoDB Connection

The application connects to MongoDB at `mongodb://localhost:27017/userDB`. To modify this:

1. Open `app.js`
2. Find the line: `mongoose.connect("mongodb://localhost:27017/userDB")`
3. Replace with your MongoDB connection string

## ▶️ Running the Application

1. **Start MongoDB** (if running locally)
   ```bash
   mongod
   ```

2. **Start the server**
   ```bash
   npm start
   ```
   Or manually:
   ```bash
   node app.js
   ```

3. **Access the application**
   - Open your browser
   - Navigate to: `http://localhost:3000`

You should see the Secrets home page with Register and Login buttons.

## 📁 Project Structure

```
Secrets/
├── app.js                 # Main Express application & routes
├── package.json          # Project dependencies & metadata
├── README.md             # This file
├── .env                  # Environment variables (not in repo)
├── public/
│   └── css/
│       └── styles.css    # Custom CSS styles
└── views/
    ├── home.ejs          # Homepage
    ├── login.ejs         # Login page
    ├── register.ejs      # Registration page
    ├── secrets.ejs       # Secrets dashboard (authenticated)
    ├── submit.ejs        # Submit secret form
    └── partials/
        ├── header.ejs    # Header template (Bootstrap & meta tags)
        └── footer.ejs    # Footer template
```

## 🌐 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Home page |
| GET | `/register` | Registration form |
| GET | `/login` | Login form |
| GET | `/secrets` | Secrets dashboard (requires auth) |
| GET | `/submit` | Submit secret form (requires auth) |
| POST | `/register` | Create new user account |
| POST | `/login` | Authenticate user |
| POST | `/submit` | Save a secret |

## 🔒 Security Features

### Password Encryption
- **Method**: mongoose-encryption with secret key
- **Plugin**: Automatically encrypts/decrypts password fields
- **Configuration**: Specified in userSchema via plugin parameters

### Best Practices Implemented
- Environment variables for sensitive data (SECRET key)
- Server-side password validation
- Database field encryption
- HTTPOnly form submissions

### Recommended Enhancements
- Implement JWT token-based authentication
- Add HTTPS/SSL support
- Use bcrypt for password hashing (more secure than field encryption)
- Add CSRF protection
- Implement rate limiting
- Add input validation & sanitization
- Use sessions for secure auth state

## 📱 Responsive Design

The application features a fully responsive design that adapts to all screen sizes:

- **Mobile-First Approach**: Optimized for small screens first
- **Bootstrap Grid System**: Flexible layout using Bootstrap's grid
- **Flexible Cards & Forms**: Responsive form layouts
- **Touch-Friendly**: Appropriately sized buttons for mobile
- **Mobile Navigation**: Properly spaced navigation elements

### Breakpoints
- **Mobile**: < 576px
- **Tablet**: 576px - 768px
- **Desktop**: > 768px

## 🎨 Customization

### Styling
Edit `public/css/styles.css` to customize:
- Colors & themes
- Typography
- Spacing & layouts
- Animations & transitions

### Templates
Modify EJS templates in `views/` to:
- Change page content
- Restructure layouts
- Add new features

## 🤝 Contributing

Feel free to fork, modify, and enhance this project!

## 📝 License

ISC License - See package.json for details

---

**Last Updated**: May 2026
**Version**: 1.0.0
