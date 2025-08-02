# 📰 NewsHub API

A full-featured backend API for publishing and consuming news articles. Designed with modern backend principles, it includes **Authentication**, **Authorization**, **Email Verification**, **Pagination**, **Redis Caching**, **Rate Limiting**, **Dockerized Redis**, and more.

---

## 🚀 Features

- ✅ **User Authentication & Authorization** (JWT-based)
- 📝 **CRUD News Management**
- 🔍 **Advanced Search, Filter & Pagination**
- 🔄 **Redis Caching for Performance**
- 📧 **Email Notification via Nodemailer**
- 📦 **Rate Limiting with Express**
- 🧰 **Helmet & CORS for Security**
- 🐳 **Dockerized Redis Integration**
- 🔁 **Queue-ready structure for scalability**
- 📁 **News Images Upload & Removal**

---

## 🧠 Core Backend Concepts Used

### 🔐 Authentication & Authorization
- Users must register/login to access protected routes.
- JWT is used for token-based secure access.
- Authorization logic restricts update/delete to only the **creator** of a news item.

### 🛡️ CORS & Security (Helmet)
- Configured CORS to handle cross-origin requests.
- Used **Helmet** to add security headers and prevent common attacks (XSS, clickjacking).

### ⚙️ Rate Limiting
- Prevents abuse by limiting API calls based on **client IP address**.
- Uses `express-rate-limit` to restrict requests per window (e.g. 100 requests per 15 mins).

### ⚡ Redis Caching
- **Boosts performance** by serving news from cache if data doesn't change frequently.
- Integrated via **Dockerized Redis**.
- Automatically **invalidates** cache after data mutation (add/delete).

### 🔁 Pagination
- Custom pagination using `page` and `limit` query.
- Implemented with formula:
- Helps avoid over-fetching, especially for mobile clients or slow networks.

### 📨 Email Sending with Nodemailer
- Sends automated emails on **registration**, **contact requests**, or **news notifications**.
- Built using `nodemailer` with SMTP configuration.
- Ready to integrate for:
- Email Verification
- Password Reset
- News Alert Subscriptions

### 🔄 API Transformation
- Only **relevant data** is exposed in API responses.
- Utilizes `select` in Prisma to shape the response body (e.g., removing password from user data).
- Helpful for mobile apps and frontends that require specific fields only.

### 🔃 Queue (Scalable Ready)
- **Planned**: Queue system using **BullMQ + Redis** for:
- Email processing
- Background jobs
- Image processing
- Queue integration will decouple user-facing APIs from heavy background operations.

---

## 🛠️ Tech Stack

| Category     | Tech                            |
|--------------|----------------------------------|
| Language     | JavaScript (Node.js)            |
| Framework    | Express.js                      |
| ORM          | Prisma + PostgreSQL             |
| Auth         | JWT, Bcrypt                     |
| Caching      | Redis (via Docker)              |
| Email        | Nodemailer                      |
| Pagination   | Manual `skip` + `take`          |
| File Uploads | File System (Image Handling)    |
| Security     | Helmet, CORS                    |
| Dev Tools    | Winston Logger, Nodemon         |

---

## 🧪 API Endpoints

| Method | Endpoint             | Description              |
|--------|----------------------|--------------------------|
| POST   | `/api/auth/register` | Register user            |
| POST   | `/api/auth/login`    | Login user               |
| GET    | `/api/news/`         | Fetch news (paginated)   |
| GET    | `/api/news/:id`      | Fetch single news item   |
| POST   | `/api/news/`         | Create news (auth)       |
| PUT    | `/api/news/:id`      | Update news (auth + owner)|
| DELETE | `/api/news/:id`      | Delete news (auth + owner) |

Supports:
- `?page=2&limit=5`
- `?search=term`

---

## 🧱 Project Structure

