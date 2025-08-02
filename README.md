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

