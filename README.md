# E-Commerce Platform

A modern online shopping application built with React + TypeScript + Tailwind CSS on the frontend and Node.js + Express + MongoDB on the backend.

## Features

- Customer auth with JWT and password hashing
- Product listing with filtering, sorting, and search
- Product detail page with reviews and related products
- Cart and wishlist management
- Checkout with shipping and payment flow
- Orders and order tracking
- Admin dashboard with analytics and product management
- Stripe payment integration mock/test fallback
- Responsive UI with premium styling

## Tech Stack

- Frontend: React, Vite, TypeScript, Tailwind CSS, Redux Toolkit, React Router, Axios, React Hook Form, Zod
- Backend: Node.js, Express, TypeScript, Mongoose, JWT, bcrypt, Stripe
- Database: MongoDB
- Storage: Cloudinary-ready with local fallback support

## Project Structure

```bash
project/
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── vite.config.ts
│   └── tailwind.config.js
├── backend/
│   ├── src/
│   ├── package.json
│   └── tsconfig.json
├── .env.example
├── README.md
├── package.json
└── .gitignore
```

## Prerequisites

- Node.js 18+
- npm 9+
- MongoDB running locally or a MongoDB Atlas connection string
- Stripe test account (optional for live payment flows)

## Installation

1. Clone the repo and install dependencies:

```bash
npm install
npm run install:all
```

2. Copy environment variables:

```bash
cp .env.example .env
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env
```

3. Update values in `.env` files as needed.

## Environment Variables

Root `.env`:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/ecommerce-app
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d
CLIENT_URL=http://localhost:5173
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
```

Backend `.env` can mirror the same values or include app-specific settings.

## Run Development Servers

```bash
npm run dev
```

This starts:
- Backend on: http://localhost:5000
- Frontend on: http://localhost:5173

## Seed Database

```bash
npm run seed
```

This creates:
- admin user
- sample customer
- categories
- 20 realistic products
- coupons and review data

## Production Build

```bash
npm run build
```

To run the backend production build:

```bash
npm run start --prefix backend
```

To preview the frontend production build:

```bash
npm run preview --prefix frontend
```

## Default Admin Account

```text
Email: admin@shop.com
Password: Admin123!
```

## API Highlights

### Auth
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`

### Products
- `GET /api/products`
- `GET /api/products/:id`
- `POST /api/products`
- `PUT /api/products/:id`
- `DELETE /api/products/:id`

### Orders
- `POST /api/orders`
- `GET /api/orders`
- `GET /api/orders/:id`
- `PUT /api/orders/:id/status`

### Cart
- `GET /api/cart`
- `POST /api/cart`
- `PUT /api/cart/:id`
- `DELETE /api/cart/:id`

### Payment
- `POST /api/payment/create-checkout-session`
- `POST /api/payment/webhook`

## Admin Access

Admin-only routes are protected with role-based middleware by checking the authenticated user role.

## Deployment Notes

- Deploy backend to Render, Railway, or a VPS
- Deploy frontend to Vercel or Netlify
- Set production environment variables securely
- Use Stripe test keys in development and live keys in production

## Licence

MIT
