# React Jobs Board

A full-featured React application for browsing, adding, editing, and deleting job postings. Built with Tailwind CSS and React Router, it connects to any RESTful API (e.g. JSON Server) to perform all CRUD operations.

---

## Features

- **Browse Jobs**: View all job listings with optional “featured” (home) limit.  
- **Job Details**: See full job information, including description, salary, location, and company info.  
- **Add Job**: Fill out a form to create a new job posting.  
- **Edit Job**: Update an existing job via a pre-filled form.  
- **Delete Job**: Remove a job posting with confirmation.  
- **Notifications**: Success/error toasts for create, update, and delete actions.  
- **404 Handling**: Friendly “Not Found” page for non-existent routes.  

## Technologies

- **React** (v18+)  
- **React Router DOM** (v6)  
- **React Toastify** (notifications)  
- **Tailwind CSS** (utility-first styling)  
- **React Icons**  
- **JSON Server** (or any REST API backend)  

## Getting Started

1. **Clone repo**  
   ```bash
   git clone https://github.com/your-username/react-jobs-board.git
   cd react-jobs-board
   ```

2. **Install dependencies**  
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Run JSON Server** (if using JSON Server)  
   ```bash
   npx json-server --watch db.json --port 8000
   ```

4. **Start development server**  
   ```bash
   npm start
   # or
   yarn start
   ```

5. **Open** [http://localhost:3000](http://localhost:3000)  

---

## Pages & Components

### Pages

- **HomePage**  
  Landing page that renders `Hero`, `HomeCards`, a limited `JobListings`, and “View All Jobs” link.

- **JobsPage**  
  Shows all jobs via `JobListings`.

- **JobPage**  
  Displays detailed info for one job, with “Edit” and “Delete” controls. Uses `useLoaderData` and a loader to fetch `/jobs/:id`.

- **AddJobPage**  
  Form to create a new job (title, type, description, salary, location, company name/description, contact email/phone).

- **EditJobPage**  
  Same form as Add, but pre-filled with existing data; submits updates to `/jobs/:id`.

- **NotFoundPage**  
  404 page for unmatched routes.

### Reusable Components

- **Navbar**  
  Top navigation with links to Home, Jobs, Add Job; displays brand logo.

- **Hero**  
  Banner section with title and subtitle props.

- **HomeCards**  
  Two promo cards (“For Developers” → Jobs, “For Employers” → Add Job).

- **Card**  
  Generic wrapper with `bg` prop for background color, padding, rounded corners, shadow.

- **JobListings**  
  Fetches `/jobs` (limit via `isHome`), shows loading spinner, renders a grid of `JobListing`.

- **JobListing**  
  Card showing job title, type, location, truncated description with “More/Less” toggle, salary, and a “View Details” link.

- **Spinner**  
  Simple loading indicator while API requests are in flight.

---

## API Endpoints

Assuming backend at `http://localhost:8000`:

| Method | Endpoint             | Description                  |
| ------ | -------------------- | ---------------------------- |
| GET    | `/jobs`              | List all jobs                |
| GET    | `/jobs?_limit=3`     | List first 3 (featured)      |
| GET    | `/jobs/:id`          | Get one job by ID            |
| POST   | `/jobs`              | Create new job               |
| PUT    | `/jobs/:id`          | Update existing job          |
| DELETE | `/jobs/:id`          | Delete job                   |

---

