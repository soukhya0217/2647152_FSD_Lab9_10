# Dairy Management System
A modern, responsive dairy management dashboard built with Next.js and Tailwind CSS.
Demonstrates Server-Side Rendering (SSR), Client-Side Rendering (CSR), and API-based data fetching.
Includes farmer management, milk collection, validation, filtering, and a premium mobile-first UI.






# DairyFlow - Modern Dairy Management System

A complete, modern Dairy Management System built with Next.js, React, and Tailwind CSS.
This dashboard handles the daily operations of a dairy cooperative, including farmer profiles and milk collection records.

## Project Overview

"DairyFlow" is designed as a professional SaaS-style dashboard, moving away from simple college CRUD layouts. It features:
- Mobile-first, responsive design
- Realistic data structures for the Indian dairy context
- Clean UI with subtle shadows, rounded corners, and sensible typography
- Form validations with user-friendly error messages

## Technologies Used

- **Framework**: Next.js 15 (App Router)
- **Library**: React 19
- **Styling**: Tailwind CSS 4
- **Icons**: Lucide React
- **Data Fetching**: Fetch API
- **Fonts**: Geist (Sans & Mono)

## How to Install

1. Ensure you have Node.js installed.
2. Navigate to the project directory.
3. Install the dependencies:
   ```bash
   npm install
   ```

## How to Run

Start the development server:
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

## SSR vs CSR in this Project

This project clearly demonstrates both rendering strategies used in Next.js.

### Server-Side Rendering (SSR)
- **Location**: `app/page.js` (DashboardPage)
- **Description**: The main dashboard fetches aggregate dairy data (`/api/dashboard`) on the server *before* rendering the HTML. This ensures fast initial load, SEO benefits, and that the user sees the data immediately without a loading spinner.
- **Implementation**: Uses standard async/await inside the Server Component without `"use client"`.

### Client-Side Rendering (CSR)
- **Location**: `components/RecentCollections.jsx`, `app/farmers/page.js`, `app/collections/page.js`
- **Description**: Highly interactive components like tables with search, filter, and forms use CSR. Data is fetched in the browser after the initial page load.
- **Implementation**: Uses `"use client"`, `useState`, `useEffect`, and `fetch` to load data, showing a loading state (skeletons/spinners) while fetching.

## API Routes

The backend uses Next.js Route Handlers to simulate a REST API:
- `GET /api/dashboard` - Returns summary stats for the dashboard.
- `GET /api/farmers` - Returns a list of active and inactive farmers.
- `POST /api/farmers` - Accepts a new farmer payload.
- `GET /api/collections` - Returns recent milk collection records.
- `POST /api/collections` - Accepts a new milk collection payload.

## Tailwind CSS Usage

Tailwind utility classes are used extensively throughout the application. `globals.css` is kept minimal, only defining custom font variables and the base body background color. All responsiveness (e.g., `sm:`, `md:`, `lg:` prefixes), hover states (`hover:`), and layout structures (`flex`, `grid`) are handled directly in the JSX using Tailwind.

## Project Structure

```
.
├── app/
│   ├── api/
│   │   ├── dashboard/route.js
│   │   ├── collections/route.js
│   │   └── farmers/route.js
│   ├── collections/page.js
│   ├── farmers/page.js
│   ├── globals.css
│   ├── layout.js
│   └── page.js
└── components/
    ├── Header.jsx
    ├── Sidebar.jsx
    ├── RecentCollections.jsx
    ├── FarmerForm.jsx
    └── CollectionForm.jsx
```
