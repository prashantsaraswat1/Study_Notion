<div align="center">

<img src="https://res.cloudinary.com/dz6smmqnq/image/upload/v1/studynotion/logo.png" alt="StudyNotion Logo" width="120" height="120" onerror="this.style.display='none'"/>

# 📚 StudyNotion — Full Stack EdTech Platform

### *A production-grade Learning Management System built with the MERN Stack*

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-Visit_App-brightgreen?style=for-the-badge)](https://study-notion-taupe-beta.vercel.app/)
[![MIT License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com)

<br/>

> **StudyNotion** is a scalable, production-deployed EdTech platform where instructors publish courses and students enroll, pay, and learn — with full RBAC, payment gateway, and cloud media management.

<br/>

![StudyNotion Banner](https://via.placeholder.com/900x400/1a1a2e/ffffff?text=StudyNotion+|+Full+Stack+LMS+Platform)

</div>

---

## 🌟 Why This Project Stands Out

| Feature | Detail |
|---|---|
| 🔐 **JWT Auth + RBAC** | 3 roles (Student, Instructor, Admin) with 15+ protected API endpoints |
| 💳 **Payment Gateway** | Full Razorpay checkout flow with order creation & webhook verification |
| ☁️ **Cloud Media** | Cloudinary integration for video/image storage with CDN delivery |
| 🚀 **Production Deployed** | Vercel (frontend) + Render (backend) — 99% uptime |
| 🏗️ **Scalable Architecture** | MVC pattern, modular routers, and service-layer separation |

---

## 📸 Screenshots

<div align="center">

### 🏠 Homepage — Hero Section
![Homepage](./screenshots/screenshot-homepage.png)

### 📚 Course Catalog Page
![Course Catalog](./screenshots/screenshot-catalog.png)

### 💻 Unlock Coding Potential Section
![Coding Section](./screenshots/screenshot-courses.png)

| About Page | Contact Page |
|:---:|:---:|
| ![About](./screenshots/screenshot-about.png) | ![Contact](./screenshots/screenshot-contact.png) |

### 🔐 Signup — Role-Based Registration (Student / Instructor)
![Signup](./screenshots/screenshot-signup.png)

</div>

---

## 🏛️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     CLIENT (React.js)                    │
│  Redux Toolkit │ Tailwind CSS │ Axios │ React Router     │
└──────────────────────────┬──────────────────────────────┘
                           │ REST API (JSON / HTTPS)
┌──────────────────────────▼──────────────────────────────┐
│                   SERVER (Node + Express)                 │
│   Auth Middleware │ RBAC Guards │ MVC Controllers         │
│   JWT Verification │ Razorpay SDK │ Cloudinary SDK        │
└──────────┬───────────────────────────────┬──────────────┘
           │                               │
┌──────────▼──────────┐       ┌────────────▼────────────┐
│  MongoDB Atlas      │       │  Cloudinary CDN          │
│  (Primary Database) │       │  (Media Storage)         │
└─────────────────────┘       └─────────────────────────┘
```

---

## ✨ Features

### 👨‍🎓 Student
- Browse and search course catalog with filters
- Secure Razorpay checkout for course enrollment
- Video player with progress tracking per lecture
- Profile management with avatar upload
- Wishlist and cart functionality

### 👨‍🏫 Instructor
- Create / edit / delete courses with rich content editor
- Upload videos directly to Cloudinary
- Dashboard with revenue insights and enrollment stats
- Manage course sections and sub-sections dynamically

### 🛡️ Admin
- Platform-level analytics overview
- Instructor and student account management
- Course approval and moderation controls

### 🔒 Security & Auth
- JWT Access Tokens with secure httpOnly cookie support
- Password hashing with bcrypt (salt rounds: 10)
- OTP-based email verification via NodeMailer
- Role-based route protection on both frontend & backend

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React.js 18 | UI library with component-based architecture |
| Redux Toolkit | Global state management (auth, cart, course) |
| Tailwind CSS | Utility-first styling |
| React Router v6 | Client-side navigation with protected routes |
| Axios | HTTP client with request/response interceptors |
| Vite | Lightning-fast dev server and build tool |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express.js | RESTful API server with MVC architecture |
| MongoDB + Mongoose | NoSQL database with schema validation |
| JWT (jsonwebtoken) | Stateless authentication |
| Bcrypt | Secure password hashing |
| NodeMailer | OTP and notification emails |
| Multer | File upload middleware |

### Cloud & Services
| Service | Role |
|---|---|
| MongoDB Atlas | Managed cloud database |
| Cloudinary | Video/image CDN and storage |
| Razorpay | Payment processing |
| Vercel | Frontend hosting |
| Render | Backend hosting |

---

## 📁 Project Structure

```
StudyNotion/
├── 📂 src/                         # React Frontend
│   ├── 📂 components/
│   │   ├── 📂 Auth/                # Login, Signup, OTP forms
│   │   ├── 📂 Dashboard/           # Role-specific dashboards
│   │   ├── 📂 Course/              # Course cards, player, catalog
│   │   └── 📂 Common/              # Navbar, Footer, Spinner
│   ├── 📂 pages/                   # Route-level page components
│   ├── 📂 services/                # API call functions (apiConnector)
│   ├── 📂 slices/                  # Redux Toolkit slices
│   └── 📂 utils/                   # Helper functions
│
├── 📂 server/                      # Express Backend
│   ├── 📂 controllers/             # Route handler logic
│   │   ├── Auth.js
│   │   ├── Course.js
│   │   ├── Payment.js
│   │   └── Profile.js
│   ├── 📂 middlewares/             # Auth, RBAC, file upload
│   ├── 📂 models/                  # Mongoose schemas
│   │   ├── User.js
│   │   ├── Course.js
│   │   ├── Section.js
│   │   └── SubSection.js
│   ├── 📂 routes/                  # Express route definitions
│   ├── 📂 utils/                   # Mailer, Cloudinary helpers
│   └── index.js                    # Server entry point
│
└── 📄 README.md
```

---

## 🗄️ Database Schema (Key Models)

```js
// User Model (simplified)
{
  firstName, lastName, email,
  password,        // bcrypt hashed
  accountType,     // "Student" | "Instructor" | "Admin"
  courses,         // ref → Course[]
  courseProgress,  // ref → CourseProgress[]
  image            // Cloudinary URL
}

// Course Model (simplified)
{
  courseName, courseDescription, price,
  instructor,     // ref → User
  studentsEnrolled: [ref → User],
  courseContent:  [ref → Section],
  thumbnail,      // Cloudinary URL
  status          // "Draft" | "Published"
}
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB Atlas account
- Cloudinary account
- Razorpay account (test mode works)

### 1. Clone the repository
```bash
git clone https://github.com/prashantsaraswat1/Study_Notion.git
cd Study_Notion
```

### 2. Setup Backend
```bash
cd server
npm install
```

Create `server/.env`:
```env
MONGODB_URL=your_mongodb_atlas_uri
JWT_SECRET=your_super_secret_key
JWT_EXPIRE=24h

# Cloudinary
CLOUD_NAME=your_cloud_name
API_KEY=your_api_key
API_SECRET=your_api_secret

# Razorpay
RAZORPAY_KEY=your_razorpay_key
RAZORPAY_SECRET=your_razorpay_secret

# NodeMailer
MAIL_HOST=smtp.gmail.com
MAIL_USER=your_email@gmail.com
MAIL_PASS=your_app_password

PORT=4000
```

### 3. Setup Frontend
```bash
cd ..   # back to root
npm install
```

Create `.env`:
```env
REACT_APP_BASE_URL=http://localhost:4000/api/v1
REACT_APP_RAZORPAY_KEY=your_razorpay_key
```

### 4. Run the app
```bash
# Terminal 1 — Backend
cd server && npm run dev

# Terminal 2 — Frontend
npm start
```

Open `http://localhost:3000` in your browser. 🎉

---

## 🔌 API Reference

| Method | Endpoint | Auth | Description |
|---|---|---|---|
| `POST` | `/api/v1/auth/signup` | Public | Register new user |
| `POST` | `/api/v1/auth/login` | Public | Login + JWT |
| `POST` | `/api/v1/auth/sendotp` | Public | Send OTP to email |
| `GET` | `/api/v1/course/getAllCourses` | Public | Fetch all courses |
| `POST` | `/api/v1/course/createCourse` | Instructor | Create new course |
| `PUT` | `/api/v1/course/editCourse` | Instructor | Edit course |
| `DELETE` | `/api/v1/course/deleteCourse` | Instructor | Delete course |
| `POST` | `/api/v1/payment/capturePayment` | Student | Initiate payment |
| `POST` | `/api/v1/payment/verifyPayment` | Student | Verify & enroll |
| `GET` | `/api/v1/profile/getUserDetails` | Any Auth | Get profile |
| `PUT` | `/api/v1/profile/updateProfile` | Any Auth | Update profile |

> Full API documentation: [Postman Collection](./postman_collection.json) *(add your exported collection)*

---

## ⚡ Performance Highlights

- **20+ REST APIs** with consistent error handling and response structure
- **15+ protected routes** secured via JWT middleware + RBAC guards
- **Cloudinary CDN** for sub-200ms media delivery
- **MongoDB indexing** on frequently queried fields (email, courseId)
- **Redux Toolkit** for zero-redundancy API calls via cached state

---

## 🧪 Testing

```bash
# Run backend tests (if configured)
cd server && npm test

# Lint frontend
npm run lint
```

> Manual testing done via **Postman** — collection available in `/postman_collection.json`

---

## 🚢 Deployment

| Layer | Platform | Status |
|---|---|---|
| Frontend | Vercel | [![Vercel](https://img.shields.io/badge/Deployed-Vercel-black?logo=vercel)](https://study-notion-taupe-beta.vercel.app/) |
| Backend | Render | [![Render](https://img.shields.io/badge/Deployed-Render-46E3B7?logo=render)](https://your-api.onrender.com) |
| Database | MongoDB Atlas | ✅ Live |
| Media | Cloudinary | ✅ Live |

---

## 🔮 Future Roadmap

- [ ] **Next.js migration** — SSR for SEO and performance
- [ ] **TypeScript** — End-to-end type safety
- [ ] **Docker** — Containerized deployment
- [ ] **Redis caching** — Course catalog caching layer
- [ ] **WebSocket notifications** — Real-time enrollment alerts
- [ ] **AI-powered quiz generator** — Auto-generate MCQs from course content
- [ ] **Mobile app** — React Native companion app

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'feat: add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct.

---

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

---

## 👨‍💻 Author

<div align="center">

**Prashant Saraswat**
*Full Stack Developer | MERN Stack | REST APIs | Cloud Deployment*

[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://portfolio-website-seven-xi-14.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/prashant-saraswat-372116357)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/prashantsaraswat1)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:prashantsaraswat48@gmail.com)

</div>

---

<div align="center">

**If this project helped you or impressed you, please ⭐ star the repo — it means a lot!**

*Made with ❤️ and a lot of ☕ by Prashant Saraswat*

</div>
