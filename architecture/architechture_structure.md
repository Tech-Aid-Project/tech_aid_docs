# 🏛️ Tech Aid – Software Architecture

**Tech Aid** is an educational platform focused on **digital inclusion** with a focus on accessibility and gamification. This architecture adopts the **microservices** style to ensure modularity, scalability and independence between components.

---

## 🗂️ Project Structure


# 🏛️ Architecture
```
tech-aid/
├── auth-service/  #  Registration, login, authentication with JWT.
├── user-profile-service/ # Storing and managing user profiles.
├── content-service/      # CRUD of lessons, videos, quizzes and materials.
├── gamification-service/ # Points rules, progress, badges and achievements.
├── notification-service/ # Sending emails and messages (e.g. WhatsApp, SMS).
├── front-end/            # Consumes APIs from microservices and displays the interface to the user.
├── tech-aid-infra        # docker-compose, k8s configs, etc.
└── tech-aid-docs         # arquitetura, wireframes, artigos, estudos
```
```
[User]
 ↓
[Frontend (React)]
 ↓
[API Gateway]
 ┌────────────┬────────────── ┬────────────┬──────────────┐
 ↓ ↓ ↓ ↓ ↓
Auth User Profile Content Gamification Notifications
Service Service Service Service Service
```

## 🔧 Microservices

### `1. auth-service`
- **Responsible for**: Registration, login, authentication with JWT.
- **Stack**: Node.js + Express + PostgreSQL + bcrypt + JWT + Prisma.
- **Endpoints**:
- `POST /register`
- `POST /login`
- `GET /verify-token`

---

### `2. user-profile-service`
- **Responsible for**: Storing and managing user profiles.
- **Stack**: Node.js + PostgreSQL + Axios + TypeScript + Express + Prisma.
- **User fields**: name, age, email, preferences, progress, accessibility settings.
- **Endpoints**:
- `GET /users/:id`
- `PUT /users/:id`
- `GET /users/:id/progress`
- `PATCH /users/:id/progress`
- `DELETE /users/:id`

---

### `3. content-service`
- **Responsible for**: CRUD of lessons, videos, quizzes and materials.
- **Stack**: Node.js + PostgreSQL + Axios + TypeScript + Express + Prisma.
- **Endpoints**:
- `GET /lessons`
- `POST /lessons`
- `PUT /lessons/:id`
- `DELETE /lessons/:id`

---

### `4. gamification-service`
- **Responsible for**: Points rules, progress, badges and achievements.
- **Stack**:Node.js + PostgreSQL + Axios + TypeScript + Express + Prisma.
- **Endpoints**:
- `GET /users/:id/points`
- `POST /users/:id/points`
- `GET /leaderboard`

---

### `5. notification-service` 
- **Responsible for**: Sending emails and messages (e.g. EMAIL).
- **Stack**: Node.js + PostgreSQL + Axios + TypeScript + Express + Nodemailer + Prisma.
- **Usage**: Scheduling reminders, congratulations, lesson confirmations.
- **Endpoints**:
- `POST /notifications/email`
- `POST /notifications/:id`
- `GET /verify-token`

---
### `6. front-end`
- **Function**: Consumes APIs from microservices and displays the interface to the user.
- **Stack**: React (with Vite or CRA) + Tailwind CSS + Axios.
- **Highlights**:
- Modern componentization
- Accessibility support (ARIA, large font, high contrast)
- React Router for navigation
- Context API or Zustand for global state
## 🛢️ Database

| Service | Database | Rationale |
|------------------------|--------------------|--------------------------------------------------|
| `auth-service` | PostgreSQL | Critical data consistency and integrity |
| `user-profile-service` | MongoDB | Flexibility for user preferences |
| `content-service` | MongoDB | Dynamic framework for educational content |
| `gamification-service` | Redis + PostgreSQL | Cache for speed + achievement persistence |
| `notification-service` | Redis + PostgreSQL | Queue + log of sent notifications |

---

## 📦 Orchestration (Docker)

The `docker-compose.yml` centralizes all services:
- Each microservice in its container.
- Database coupled to each service.
- HTTP communication between services.

---
## ☁️ Hosting

| Component | Recommended service |
|------------|--------------------------|
| Front-end | Vercel / Netlify |
| Back-end | Railway / Render / Fly.io|
| DB | MongoDB Atlas / Supabase|

---
## 🎮 Gamification

- Achievements unlocked based on actions (e.g. completing a class).
- Progress bar and level system.
- Simple and stimulating visual rewards.

---
## ♿ Accessibility

- High contrast buttons.
- Large and legible font.
- Smooth animations.
- Compatibility with screen readers.
- Simple navigation with visual and textual feedback.
- Night mode
