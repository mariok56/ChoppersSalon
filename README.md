Choppers Salon – Full‑Stack Hair Salon Web App

Choppers Salon is a full‑stack hair‑salon platform built with React + TypeScript on top of Vite and [Tailwind CSS]. It uses the Shadcn UI component library and Radix primitives to deliver a clean, responsive interface. The site includes a marketing homepage, service catalogue, multi‑step appointment booking, authentication and a back‑office admin portal. Data is stored in Firebase Firestore, authentication is handled via Supabase, and state management uses Zustand. The project started as an auto‑generated Anima design but has been expanded into a real‑world product.

✨ Key Features
🌟 Landing page

A hero section with a welcome message, tagline and call‑to‑action buttons. Visitors can click “Book Now” to jump straight into the booking flow or “All Services” to browse the services catalogue
raw.githubusercontent.com
.

Responsive image and overlay ensures the design looks great on desktop and mobile
raw.githubusercontent.com
.

💇‍♀️ Services catalogue

Categories for Haircuts, Coloring, Styling and Treatments with a tabbed interface to switch between them
raw.githubusercontent.com
.

Each service card displays the service name, description, price and duration
raw.githubusercontent.com
 and includes a “Book Now” button that takes users to the booking flow
raw.githubusercontent.com
.

The catalogue is data‑driven; you can add or modify categories and services via Firestore or the admin portal.

📆 Appointment booking (protected route)

Multi‑step flow that guides users through Service selection → Stylist selection → Date → Time → Confirmation
raw.githubusercontent.com
raw.githubusercontent.com
.

Data is fetched from Firestore on mount, including salon settings, services and stylists
raw.githubusercontent.com
.

Users can manage existing appointments via a Manage Appointments tab
raw.githubusercontent.com
.

🔐 Authentication & protected routes

Sign‑in and sign‑up pages using Supabase; password hashing via bcryptjs.

The booking page and admin pages are wrapped in a ProtectedRoute component so only authenticated users can book or access the dashboard
raw.githubusercontent.com
.

🛒 Shop & e‑commerce (coming soon)

A Shop page (placeholder) ready to showcase and sell hair products and accessories.

🧑‍💼 Admin dashboard

Accessed via /admin, the back‑office portal allows salon staff to manage the business.

Overview: displays metrics such as total users, today’s appointments, revenue and total products, calculated from Firestore collections
raw.githubusercontent.com
.

Users: lists all users with search functionality; admins can toggle a user’s role between admin and user
raw.githubusercontent.com
.

Appointments: lists all appointments, supports filtering (all / upcoming / completed / cancelled) and allows marking an appointment as completed or cancelled
raw.githubusercontent.com
raw.githubusercontent.com
.

Orders & Products: placeholders ready for integration with a commerce back end.

Settings: manage salon settings such as working hours and contact details.

📱 Responsive design & dark mode

Fully responsive layouts built with Tailwind CSS and custom classes.

Dark theme styling with gray backgrounds and accent colours (yellow/orange) as shown in the code snippets.

📧 Email templates

emailTemplates.ts contains ready‑to‑use HTML templates for sending booking confirmations and password reset emails.

🧰 Tech Stack
Layer	Technologies
Frontend	React 18, TypeScript, Vite, React Router v7, Zustand state management, React Hook Form + Zod for forms
Styling	Tailwind CSS, Shadcn UI components, Radix UI primitives, custom fonts (Poppins & Jost)
Backend	Firebase Firestore (services, stylists, appointments, orders, products), Supabase for authentication
Utilities	Lucide‑React icons, Lodash, Class‑variance‑authority (cva) for styling variants
📂 Project Structure (simplified)
ChoppersSalon/
├─ public/                     # Static assets (images, icons, fonts)
├─ src/
│  ├─ components/             # Shared components (Navbar, Footer, ProtectedRoute, etc.)
│  ├─ config/                 # Supabase and Firebase configuration
│  ├─ routes/router.tsx       # Route definitions for user and admin areas:contentReference[oaicite:14]{index=14}
│  ├─ screens/
│  │  ├─ Home.tsx             # Landing page with hero and CTA buttons:contentReference[oaicite:15]{index=15}
│  │  ├─ Services.tsx         # Services catalogue with categories and service cards:contentReference[oaicite:16]{index=16}:contentReference[oaicite:17]{index=17}
│  │  ├─ booking/             # Multi‑step booking flow (service, stylist, date, time, confirmation)
│  │  ├─ admin/               # Admin pages (Dashboard, Overview, Users, Appointments, Orders, Products, Settings)
│  │  ├─ Auth/                # Login and Register pages
│  │  ├─ Contact.tsx          # Contact form and salon location
│  │  ├─ About.tsx            # About page with salon history and team
│  │  └─ Shop.tsx             # Shop page (placeholder)
│  ├─ store/                  # Zustand stores (authStore, bookingStore)
│  ├─ utils/                  # Helper functions and constants
│  └─ App.tsx                 # Top‑level component mounting routes
├─ tailwind.config.js         # Tailwind customisation (colours, fonts, etc.)
├─ package.json               # Project metadata and dependencies:contentReference[oaicite:18]{index=18}
└─ README.md                  # Project overview (you are reading it)

🚀 Getting Started

Prerequisites: You need Node.js installed on your system.
The default config expects Firebase and Supabase credentials; create accounts and collect your keys before running the app.

Clone the repository

git clone https://github.com/mariok56/ChoppersSalon.git
cd ChoppersSalon


Install dependencies (one time):

npm install


Configure environment variables:

Copy .env.example to .env (create one if it doesn’t exist).

Set the following variables with your own keys:

VITE_SUPABASE_URL=<your-supabase-url>
VITE_SUPABASE_ANON_KEY=<your-supabase-anon-key>

VITE_FIREBASE_API_KEY=<your-firebase-api-key>
VITE_FIREBASE_AUTH_DOMAIN=<your-firebase-auth-domain>
VITE_FIREBASE_PROJECT_ID=<your-firebase-project-id>
VITE_FIREBASE_STORAGE_BUCKET=<your-firebase-storage-bucket>
VITE_FIREBASE_MESSAGING_SENDER_ID=<your-firebase-messaging-sender-id>
VITE_FIREBASE_APP_ID=<your-firebase-app-id>


Run the development server:

npm run dev


After a few seconds the app will be available at http://localhost:5173
 
github.com
.

Build for production:

npm run build


The compiled files will be output to the dist/ directory, ready to be deployed.

🧑‍💻 Contributing

Contributions are welcome! If you find a bug or want to propose a new feature:

Fork this repository and create a branch for your feature or bugfix.

Make your changes and commit with clear messages.

Open a pull request describing your changes and reference any related issues.

Please follow the existing coding style and file structure. Issue reports and suggestions via GitHub Issues are also appreciated.

📄 License

This project is provided for educational and portfolio purposes and does not yet include an official open‑source license. Feel free to clone and experiment, but please contact the author if you plan to use it in production.
