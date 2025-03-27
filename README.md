# 🏡 Rent It All - Scalable Real Estate Rental Platform

RentItAll is a modern, enterprise-grade rental apartment application built using the powerful combination of **Next.js**, **Node.js**, and **AWS cloud services**. Designed with scalability, speed, and developer ergonomics in mind, this project serves as a complete solution for deploying a real estate rental platform in production.

---

## 🚀 Tech Stack

### 🔷 Frontend
- **Next.js** (App Router)
- **TypeScript**
- **Redux Toolkit**
- **Tailwind CSS**
- **Shadcn UI**
- **Framer Motion** (animations)
- **React Hook Form** + **Zod** (form validation)

### 🟢 Backend
- **Node.js** + **Express.js** (API layer)
- **AWS EC2** (server deployment)
- **AWS RDS** (PostgreSQL database)
- **AWS S3** (image uploads)
- **AWS API Gateway** (secure API management)
- **AWS Amplify** (frontend hosting + CI/CD)

### 🔐 Authentication
- **AWS Cognito** (user pool, JWT-based auth, password management)

---

## 💡 Features

- 🏘️ List, search, and filter rental properties
- 📸 Upload images to AWS S3
- 🔐 Secure authentication via AWS Cognito
- 📦 Scalable REST API with Node.js/Express
- 🎯 Optimistic UI and UX with Tailwind, Shadcn, and Framer Motion
- ⚙️ Robust form handling using React Hook Form + Zod
- ☁️ Fully cloud-hosted (frontend + backend)

---

## 📁 Project Structure
root/ ├── frontend/ (Next.js app) │ ├── components/ │ ├── pages/ │ └── app/ ├── backend/ (Node.js + Express API) │ ├── routes/ │ ├── controllers/ │ └── models/ ├── aws/ │ └── amplify-config.json │ └── api-gateway.yaml ├── .env └── README.md

yaml
Copy
Edit

---

## 🧪 Setup & Deployment

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/rentedge.git
cd rentedge
2. Environment Variables
Create .env files in both the frontend and backend directories:

.env (Backend)
env
Copy
Edit
DB_HOST=your-rds-endpoint
DB_PORT=5432
DB_USER=admin
DB_PASSWORD=yourpassword
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
S3_BUCKET=rentedge-images
COGNITO_USER_POOL_ID=us-east-1_ABC123
COGNITO_CLIENT_ID=your-client-id
3. Install Dependencies
bash
Copy
Edit
# Frontend
cd frontend
npm install

# Backend
cd ../backend
npm install
4. Run the Application Locally
bash
Copy
Edit
# Backend
cd backend
npm run dev

# Frontend (in a separate terminal)
cd frontend
npm run dev

# rent-it-all
