# Finance Dashboard

A full-stack finance dashboard for exploring revenue, expenses, products, and transactions. The React client displays financial charts and summaries, and includes a revenue prediction view that uses linear regression. An Express API reads dashboard data from MongoDB.

## Features

- Financial dashboard with revenue, expense, and product/transaction visualizations
- Revenue trends and optional next-year projections
- Responsive dashboard layout
- REST API for KPI, product, and transaction data

## Tech stack

- **Client:** React, TypeScript, Vite, Material UI, Redux Toolkit Query, Recharts
- **Server:** Node.js, Express, Mongoose
- **Database:** MongoDB

## Requirements

- Node.js and npm
- A MongoDB instance, local or hosted

## Getting started

1. Configure the server environment in `server/.env`:

   ```env
   MONGO_URL=mongodb://localhost:27017/finance-dashboard
   PORT=8000
   ```

   `PORT` is optional; the server defaults to `8000`. Replace the MongoDB URL with your own connection string as needed.

2. Configure the client environment in `client/.env.local`:

   ```env
   VITE_BASE_URL=http://localhost:8000/
   ```

3. Install dependencies in each app:

   ```powershell
   cd server
   npm install
   cd ..\client
   npm install
   ```

4. Start the server and client in separate terminals:

   ```powershell
   cd server
   npm run dev
   ```

   ```powershell
   cd client
   npm run dev
   ```

   Open the local URL printed by Vite in your browser.

The API connects to MongoDB when the server starts. The repository includes sample records in `server/data/data.js`, but automatic database seeding is disabled; populate the database with KPI, product, and transaction documents before expecting dashboard data.

## API endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| `GET` | `/kpi/kpis/` | Retrieve KPI records |
| `GET` | `/product/products/` | Retrieve products |
| `GET` | `/transaction/transactions/` | Retrieve the 50 most recent transactions |

## Available scripts

Run these commands from the corresponding `client` or `server` directory.

### Client

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite development server |
| `npm run build` | Type-check and build the production client |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint |

### Server

| Command | Description |
| --- | --- |
| `npm run dev` | Start the API with Nodemon |
