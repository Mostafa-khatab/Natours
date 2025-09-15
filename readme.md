# Natours

This is the Natours web application from the "Complete Node.js Developer" bootcamp (Jonas Schmedtmann).

It is a full-stack Node/Express application that demonstrates REST APIs, authentication, file uploads, image processing, payments (Stripe), and sending emails.

## Contents

- `app.js` - Express application setup (middleware, routes, error handling)
- `server.js` - Entrypoint that connects to the database and starts the server
- `controllers/`, `models/`, `routes/` - Application logic
- `dev-data/` - Sample data and import script
- `public/`, `views/` - Frontend assets and Pug templates

## Requirements

- Node.js 14+ (LTS recommended)
- npm (comes with Node.js)
- MongoDB: either a local MongoDB server or a MongoDB Atlas cluster

## Quick start

1. Install dependencies

```pwsh
npm install
```

2. Create a `.env` or `config.env` file in the project root. Example environment variables required by the app:

```text
# Server
NODE_ENV=development
PORT=3000

# Database - local example
DATABASE_LOCAL=mongodb://localhost:27017/natours

# (Or) Atlas - example placeholder
# DATABASE=<your-atlas-connection-string-with-<PASSWORD>>
# DATABASE_PASSWORD=<your-db-password>

# Auth / Email / Payments
JWT_SECRET=your_jwt_secret_here
JWT_EXPIRES_IN=90d
EMAIL_USERNAME=your@example.com
EMAIL_PASSWORD=...
SENDGRID_API_KEY=SG.xxxxx
STRIPE_SECRET_KEY=sk_test_xxxxx
STRIPE_PUBLIC_KEY=pk_test_xxxxx
```

3. Run the app

```pwsh
npm start
```

The server will attempt to connect to the database and start on the configured `PORT`.

## Importing sample data

There is a script under `dev-data/import-dev-data.js` that can import sample tours, users and reviews into your database. Be careful when running it as it will overwrite data.

Example:

```pwsh
node dev-data/import-dev-data.js --import
node dev-data/import-dev-data.js --delete
```

## Important notes

- Do NOT commit secrets. This repository includes a `config.env` in the workspace for convenience; do not push that file to a public remote. Use a `.gitignore` (already included) to ignore `config.env` and `.env` files.
- If your push is blocked by GitHub push-protection because it detected secrets in earlier commits, you must remove those secrets from the commit history (rebase / filter-branch / git-filter-repo) or use GitHub's unblock flow for secret scanning.

## Troubleshooting

- If the server fails to start due to native module build errors (e.g., `sharp`), try installing production deps only:

```pwsh
npm install --omit=dev
```

- If MongoDB connection fails, verify your `DATABASE` / `DATABASE_LOCAL` values and ensure the DB server is reachable.

## License

This repository is part of a course; follow the original course license if redistributing.
# Natours Application

Built using modern technologies: node.js, express, mongoDB, mongoose and friends 😁
