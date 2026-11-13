# Student Information API
 
A RESTful backend API built with Node.js, Express, TypeScript, and Supabase PostgreSQL for **ITE 303 — Web Systems and Technologies 2**.
 
## Features
 
- Read all student records (`GET /students`)
- Read a single student record by ID (`GET /students/:id`)
- Create a new student record (`POST /students`)
- Update an existing student record (`PUT /students/:id`)
- Delete a student record (`DELETE /students/:id`)
 
## Local Setup
 
1. Install dependencies:
   ```bash
   pnpm install
   ```
2. Copy `.env.example` to `.env` and add your private Supabase PostgreSQL connection string.
3. Start the development server:
   ```bash
   pnpm dev
   ```

## Render Deployment

The Supabase CA certificate is included at `certs/supabase-ca.crt`. In Render's
environment settings, set `DATABASE_URL` to your Supabase connection string and
use the repository-relative certificate path in its query parameters:

```text
sslmode=verify-full&sslrootcert=certs%2Fsupabase-ca.crt
```

Do not use a local Windows path for `sslrootcert`; it is unavailable in Render's
Linux environment. Keep the existing `pnpm build` build command and
`pnpm run start` start command.

## API Endpoints
 
| Method | Endpoint | Description | Success Status |
| --- | --- | --- | --- |
| `GET` | `/students` | Retrieve all student records | `200 OK` |
| `GET` | `/students/:id` | Retrieve one student by ID | `200 OK` |
| `POST` | `/students` | Create a new student record | `201 Created` |
| `PUT` | `/students/:id` | Replace all editable fields of a student | `200 OK` |
| `DELETE` | `/students/:id` | Delete a student record by ID | `200 OK` |