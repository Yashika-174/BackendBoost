# 📰 NewsHub API

A robust News Management RESTful API built with **Node.js**, **Express**, and **Prisma**, featuring authentication, authorization, image upload, email sending, Redis caching, rate limiting, and more — production-ready and easily deployable.

---

## 🚀 Features

- ✅ JWT-based **Authentication & Authorization**
- 📤 News creation with **image upload**
- 📚 **Pagination** support (`page`, `limit`)
- 🔁 **Redis Caching** for fast repeated requests
- 🚦 **Rate Limiting** (per IP)
- 🔐 **Helmet** for securing headers
- 🌐 **CORS** enabled
- 📧 **Nodemailer** email notifications
- 🧰 **API Transformation** for clean responses
- 🧵 **Queue-ready** architecture (for future jobs)
- 📜 **Validation** with VineJS
- 📦 **Docker-ready** Redis

---

## 📁 Project Structure

- /controllers -> All route logic
- /middlewares -> Auth, cache, rate limit
- /routes -> Express routes
- /validations -> Schema validation
- /DB -> Prisma + Redis config
- /utils -> File/email helpers
- /transform -> Clean API responses
- /config -> Logger & mail config

---

## 🛠️ Tech Stack

- **Backend:** Node.js, Express
- **Database:** PostgreSQL (via Prisma ORM)
- **Caching:** Redis
- **Auth:** JWT, bcrypt
- **Email:** Nodemailer + SMTP
- **Image Upload:** express-fileupload
- **Logger:** Winston
- **Validation:** vinejs

---

## 🔧 Setup

```bash
git clone https://github.com/yourusername/newshub-api.git
cd newshub-api
npm install

