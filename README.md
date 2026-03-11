# Disaster_Shield

Rest-Express
A modern full-stack web application built with React, TypeScript, Express, and PostgreSQL. This project provides a robust foundation for building scalable web applications with authentication, real-time capabilities, and a beautiful UI powered by Tailwind CSS and Radix UI components.
More 

🚀 Tech Stack
Frontend

React 18 with TypeScript

Vite for fast development and building

Tailwind CSS for styling

Radix UI primitives for accessible components

React Hook Form + Zod for form validation

TanStack Query for data fetching

Wouter for lightweight routing

Recharts for data visualization

Backend

Node.js with Express

TypeScript for type safety

PostgreSQL database

Drizzle ORM with Zod integration

Passport.js for authentication (local strategy)

Express session with PostgreSQL store (connect-pg-simple)

WebSocket support (ws library) for real-time features

Twilio integration (optional)

Development Tools

TypeScript for type checking

Drizzle Kit for database migrations

ESLint (implied) and Prettier (implied)

Vite plugins for Replit environment support

📁 Project Structure
text
.
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── hooks/          # Custom React hooks
│   │   ├── lib/            # Utility functions
│   │   ├── pages/          # Page components
│   │   └── main.tsx        # Application entry point
│   └── index.html          # HTML template
├── server/                  # Backend Express application
│   ├── index.ts            # Server entry point
│   ├── routes.ts           # API route definitions
│   ├── auth.ts             # Authentication logic
│   └── db.ts               # Database connection
├── shared/                  # Shared code between client and server
│   └── schema.ts           # Drizzle schema and Zod validation
├── migrations/              # Database migration files
├── drizzle.config.ts       # Drizzle ORM configuration
├── tailwind.config.ts      # Tailwind CSS configuration
├── vite.config.ts          # Vite configuration
├── tsconfig.json           # TypeScript configuration
├── package.json            # Project dependencies and scripts
└── theme.json              # UI theme configuration (Shadcn)
🛠️ Prerequisites
Node.js 20+ (or latest LTS)

PostgreSQL 14+

npm or yarn

🔧 Setup & Installation
Clone the repository

bash
git clone <repository-url>
cd rest-express
Install dependencies

bash
npm install
Set up environment variables
Create a .env file in the root directory with the following variables:

env
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
SESSION_SECRET=your-secret-key   # Used for express-session
# Optional: Twilio credentials if using SMS features
TWILIO_ACCOUNT_SID=your-twilio-sid
TWILIO_AUTH_TOKEN=your-twilio-token
TWILIO_PHONE_NUMBER=+1234567890
Set up the database

Ensure PostgreSQL is running and create a database matching the DATABASE_URL.

Push the schema to the database (development only):

bash
npm run db:push
For production, use migrations (see below).

Run the development server

bash
npm run dev
The application will be available at http://localhost:5000 (or the port specified by process.env.PORT).

📜 Available Scripts
npm run dev – Starts the development server with hot reloading.

npm run build – Builds the frontend (Vite) and bundles the backend (esbuild) for production.

npm run start – Runs the production server (requires NODE_ENV=production and built assets).

npm run check – Runs TypeScript type checking across the project.

npm run db:push – Pushes the current Drizzle schema to the database (for development; use migrations in production).

🗄️ Database Migrations
This project uses Drizzle ORM. To manage schema changes:

Development: Use npm run db:push to sync the schema with your database. This is convenient for rapid iteration but not recommended for production.

Production: Generate migration files with drizzle-kit generate and apply them using drizzle-kit migrate. Add these scripts to package.json as needed.

Example:

bash
npx drizzle-kit generate   # Generate migration from schema changes
npx drizzle-kit migrate    # Apply migrations
🔐 Authentication
The application uses Passport.js with a local strategy for username/password authentication. Sessions are managed with express-session and stored in PostgreSQL via connect-pg-simple. To secure your application, always set a strong SESSION_SECRET in production.

🌐 Deployment
Build the project:

bash
npm run build
Set NODE_ENV=production and ensure the DATABASE_URL and SESSION_SECRET environment variables are configured.

Start the server:

bash
npm run start
For hosting, you can deploy to any Node.js-compatible platform (e.g., Render, Heroku, Railway, Replit, or a VPS). If using Replit, the configuration is already optimized.

🧩 Key Dependencies
UI Components: Radix UI primitives, Lucide icons, Tailwind CSS

Forms: React Hook Form + Zod for validation

Data Fetching: TanStack Query + Axios

Database: Drizzle ORM with PostgreSQL

Authentication: Passport.js, express-session

Real-time: WebSocket (ws) for live updates

Charts: Recharts for data visualization

📝 License
This project is licensed under the MIT License – see the LICENSE file for details (if applicable).

🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
