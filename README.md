# 🌐 Balbant Portfolio Website - Full Stack

A modern, fully responsive full-stack portfolio website built with React, Node.js, Express, MongoDB, and Tailwind CSS.

## ✨ Features

### 🎨 Frontend
- **React 18** with Vite for fast development
- **Tailwind CSS** for beautiful, responsive styling
- **Framer Motion** for smooth animations
- **Dark/Light Mode** toggle
- **Fully Responsive** - Mobile, Tablet, Desktop
- **Modern Components**:
  - Navbar with mobile menu
  - Hero section with CTA
  - About section with stats
  - Skills showcase with progress bars
  - Projects gallery
  - Testimonials carousel
  - Contact form with email integration
  - Professional footer
- **SEO Optimized** with meta tags
- **Performance Optimized** with lazy loading

### 🚀 Backend
- **Node.js + Express** REST API
- **MongoDB** database integration
- **Email Integration** with Nodemailer (Gmail SMTP)
- **Input Validation** with express-validator
- **Security Features**:
  - Helmet.js for HTTP headers
  - CORS enabled
  - Rate limiting
  - Input sanitization
- **Error Handling** middleware
- **Database Models**:
  - Contact messages
  - Projects
  - Skills

### 📦 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/health` | Health check |
| POST | `/api/contact` | Submit contact form |
| GET | `/api/contact` | Get all messages (admin) |
| GET | `/api/projects` | Get all projects |
| POST | `/api/projects` | Create project |
| GET | `/api/skills` | Get all skills |
| POST | `/api/skills` | Create skill |

---

## 📋 Prerequisites

- **Node.js** v16 or higher
- **npm** or **yarn**
- **MongoDB Atlas** account (free tier)
- **Gmail** account with app password
- **Git**

---

## 🚀 Quick Start

### 1️⃣ Clone Repository
```bash
git clone https://github.com/dilkesh01/balbantwebsite.git
cd balbantwebsite
```

### 2️⃣ Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env.local
npm run dev
```
- Open http://localhost:5173
- Start developing! 🎨

### 3️⃣ Backend Setup
```bash
cd backend
npm install
cp .env.example .env
npm run dev
```
- API runs on http://localhost:5000
- API Health: http://localhost:5000/api/health

---

## ⚙️ Configuration

### MongoDB Setup

1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create free account
3. Create new cluster (free tier)
4. Get connection string
5. Replace in `backend/.env`:

```env
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/balbant-portfolio
```

### Email Configuration (Gmail)

1. Go to Gmail account settings
2. Enable 2-factor authentication
3. Generate App Password:
   - Go to [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords)
   - Select "Mail" and "Windows Computer"
   - Copy the generated password
4. Add to `backend/.env`:

```env
EMAIL_USER=your-email@gmail.com
EMAIL_PASSWORD=your-app-specific-password
```

---

## 📁 Project Structure

```
balbantwebsite/
│
├── frontend/                 # React Application
│   ├── src/
│   │   ├── components/       # React Components
│   │   │   ├── Navbar.jsx
│   │   │   ├── Hero.jsx
│   │   │   ├── About.jsx
│   │   │   ├── Skills.jsx
│   │   │   ├── Projects.jsx
│   │   │   ├── Testimonials.jsx
│   │   │   ├── Contact.jsx
│   │   │   └── Footer.jsx
│   │   ├── styles/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── public/
│   ├── package.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── .env.example
│
├── backend/                  # Express API
│   ├── models/               # Mongoose Schemas
│   │   ├── Contact.js
│   │   ├── Project.js
│   │   └── Skill.js
│   ├── routes/               # API Routes
│   │   ├── contact.js
│   │   ├── projects.js
│   │   └── skills.js
│   ├── config/
│   │   └── db.js
│   ├── utils/
│   │   └── emailService.js
│   ├── middleware/
│   │   └── errorHandler.js
│   ├── server.js
│   ├── package.json
│   └── .env.example
│
└── README.md
```

---

## 🛠️ Development Commands

### Frontend
```bash
cd frontend

# Development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Lint code
npm run lint

# Format code
npm run format
```

### Backend
```bash
cd backend

# Development server (with auto-reload)
npm run dev

# Production server
npm start

# Run tests
npm test
```

---

## 🌍 Deployment

### Option 1: Frontend Deployment (Vercel)

1. **Push to GitHub**
```bash
git add .
git commit -m "Ready for deployment"
git push origin main
```

2. **Deploy Frontend**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import GitHub repository
   - Select `frontend` folder
   - Add environment variables:
     ```
     VITE_API_BASE_URL=https://your-backend-url.com/api
     ```
   - Deploy! ✅

### Option 2: Backend Deployment (Render.com)

1. **Push to GitHub**
   - Same as above

2. **Deploy Backend**
   - Go to [render.com](https://render.com)
   - Click "New Web Service"
   - Connect GitHub repository
   - Set root directory: `backend`
   - Build command: `npm install`
   - Start command: `npm start`
   - Add environment variables:
     ```
     MONGODB_URI=your_mongodb_uri
     EMAIL_USER=your_email@gmail.com
     EMAIL_PASSWORD=your_app_password
     FRONTEND_URL=https://your-frontend.vercel.app
     ```
   - Deploy! ✅

### Option 3: Full-Stack Deployment (Heroku/Railway)

For detailed Heroku deployment, see `DEPLOYMENT.md`

---

## 🔐 Environment Variables

### Frontend (.env.local)
```
VITE_API_BASE_URL=http://localhost:5000/api
VITE_APP_NAME=Balbant Portfolio
```

### Backend (.env)
```
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/balbant-portfolio
JWT_SECRET=your_secret_key
FRONTEND_URL=http://localhost:5173
EMAIL_USER=your-email@gmail.com
EMAIL_PASSWORD=your-app-specific-password
ADMIN_PASSWORD=admin123
```

---

## 📖 Usage Examples

### Adding a New Project

**Frontend:** Edit `src/components/Projects.jsx`
```jsx
const projects = [
  {
    title: 'My New Project',
    description: 'Project description',
    image: '🎯',
    tags: ['React', 'Node.js'],
    link: 'https://project-link.com',
    github: 'https://github.com/user/project',
  },
  // ... more projects
]
```

Or **via API:**
```bash
curl -X POST http://localhost:5000/api/projects \
  -H "Content-Type: application/json" \
  -d '{
    "title": "My Project",
    "description": "Description",
    "tags": ["React", "Node.js"],
    "link": "https://link.com",
    "github": "https://github.com/..."
  }'
```

### Adding Skills

Edit `src/components/Skills.jsx` or use API:
```bash
curl -X POST http://localhost:5000/api/skills \
  -H "Content-Type: application/json" \
  -d '{
    "category": "Frontend",
    "name": "React",
    "level": 90
  }'
```

---

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Verify connection string format
- Check IP whitelist in MongoDB Atlas
- Ensure credentials are correct

### Email Not Sending
- Verify Gmail app password (not regular password)
- Enable 2-factor authentication
- Check email configuration in `.env`

### CORS Errors
- Verify `FRONTEND_URL` in backend `.env`
- Check frontend API URL in `.env.local`

### Port Already in Use
```bash
# Kill process on port 5000 (Linux/Mac)
lsof -i :5000 | grep LISTEN | awk '{print $2}' | xargs kill -9

# Windows
netstat -ano | findstr :5000
taskkill /PID <PID> /F
```

---

## 🚀 Performance Optimizations

- ✅ Image lazy loading
- ✅ Code splitting with Vite
- ✅ CSS minification
- ✅ API response caching
- ✅ Database indexing
- ✅ Compression with gzip

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👨‍💼 About

**Balbant** - Full Stack Developer
- 🌐 Website: [balbantwebsite.com](https://balbantwebsite.com)
- 💼 GitHub: [@dilkesh01](https://github.com/dilkesh01)
- 📧 Email: dilkesh01@example.com

---

## 📞 Support

Need help? 
- 📧 Email: dilkesh01@example.com
- 🐛 Create an Issue on GitHub
- 💬 Open a Discussion

---

## 🎯 Future Enhancements

- [ ] Admin dashboard for content management
- [ ] Blog section with markdown support
- [ ] Image optimization and CDN
- [ ] Analytics integration
- [ ] Search functionality
- [ ] Comments on projects
- [ ] Newsletter signup
- [ ] Internationalization (i18n)

---

## 📊 Status

| Component | Status | Notes |
|-----------|--------|-------|
| Frontend | ✅ Complete | React + Tailwind |
| Backend | ✅ Complete | Express + MongoDB |
| Email | ✅ Configured | Gmail SMTP |
| Database | ✅ Ready | MongoDB Atlas |
| Deployment | ✅ Ready | Vercel + Render |

---

**Happy Coding! 🚀**

Made with ❤️ by Balbant | Last Updated: 2026-05-06
