# Student Attendance Management System

A production-ready web application built with Next.js (App Router), TypeScript, Tailwind CSS, shadcn/ui, and Prisma ORM.

## Prerequisites

- Node.js 18.x or later
- PostgreSQL Database (e.g., Neon, Supabase, or local Postgres)
- Git

## Local Setup

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd student-attendance-system
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   Copy the `.env.example` file to `.env` and fill in the values:
   ```bash
   cp .env.example .env
   ```
   *Note: Update the `DATABASE_URL` with your PostgreSQL connection string.*

4. **Initialize Database:**
   Push the Prisma schema to your database and generate the Prisma client:
   ```bash
   npx prisma db push
   npx prisma generate
   ```

5. **Start the development server:**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) to view the app in your browser.

## Deployment to Vercel

This app is pre-configured for Vercel deployment. The `postinstall` script in `package.json` ensures that Prisma client is generated during the Vercel build process.

1. Create a GitHub repository and push your code:
   ```bash
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

2. Log into [Vercel](https://vercel.com/) and import your repository.

3. Configure Environment Variables in Vercel:
   - `DATABASE_URL` (Your production Postgres URL)
   - `NEXTAUTH_SECRET` (Generate using `openssl rand -base64 32`)
   - `NEXTAUTH_URL` (Your Vercel deployment URL)

4. Deploy! Vercel will automatically build the Next.js app and run the `postinstall` script to generate Prisma client.
