# CineFlow – Movie Marketing Frontend

React + Vite frontend for the two modules assigned to Pionia:
- **Task 1 – Dashboard (frontend):** role selector (Admin/Manager), KPI cards, revenue/ad-spend chart, recent activity and recently added movies.
- **Task 2 – Movie Registration (frontend):** movie list, search, status summaries, registration form, cast/crew fields, synopsis, and poster/trailer file selection UI.

The other modules appear as placeholders because they are assigned to other frontend developers. This starter currently uses local mock data in React state. It is ready to connect to the Java Spring Boot APIs once backend endpoints and payloads are agreed.

## Requirements
- Node.js 18.18+ (Node.js 20 LTS recommended)
- npm

## Run locally
```bash
# 1. Extract the ZIP and open the project folder
cd movie-marketing-frontend

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```
Open the URL printed by Vite (normally http://localhost:5173).

## Production build
```bash
npm run build
npm run preview
```

## Connect to Spring Boot
Replace the mock arrays/state in `src/App.jsx` with API calls. Suggested integration points:
- `GET /api/dashboard/summary` – KPI values and chart data
- `GET /api/dashboard/activity` – activity feed
- `GET /api/movies` – movie catalogue
- `POST /api/movies` – create a movie
- `POST /api/movies/{id}/poster` and `/trailer` – upload assets
- `PATCH /api/movies/{id}/approval` – approval status

Set the backend base URL in a `.env` file, for example:
```env
VITE_API_BASE_URL=http://localhost:8080
```
For real uploads, send the selected files using `FormData`; the current upload fields only display the selected filename and do not upload to a server.

## Notes
- The Admin/Manager selector is a frontend preview control only; actual permissions must be enforced by Spring Security/RBAC on the backend.
- Movie data is stored in browser memory only and resets on refresh. Connect the APIs for persistence.
- Dashboard figures and activity are sample data for layout demonstration.
"# movie-marketing-frontend" 
