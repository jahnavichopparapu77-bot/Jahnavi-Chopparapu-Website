# Jahnavi Chopparapu Portfolio Website

A modern, production-ready personal portfolio website for Jahnavi Chopparapu, built with Next.js, TypeScript, Tailwind CSS, Prisma, Supabase PostgreSQL, and Supabase Auth.

This project is designed to support two completely different access levels:

- Public users: can only view the portfolio
- Admin: can log in and manage all portfolio content without editing source code

The goal is to create a professional, fast, accessible, SEO-friendly portfolio that is easy to maintain and update over time.

---

## Project Goal

Build a personal portfolio website that allows the owner to manage content dynamically through an admin panel.

The admin should be able to update:

- job roles
- skills
- experience
- projects
- certifications
- education
- achievements
- about section
- social links
- resume
- site settings
- homepage content

No React or Next.js source code changes should be required for these updates.

---

## Recommended Stack

Use the following stack:

- Next.js latest stable version
- App Router
- TypeScript
- Tailwind CSS
- shadcn/ui
- Lucide React icons
- Prisma ORM
- Supabase PostgreSQL
- Supabase Authentication
- next-themes
- Zod validation
- React Hook Form
- ESLint
- Prettier
- Git + GitHub
- Vercel deployment

Use Server Components by default and Client Components only where necessary for interactivity.

---

## Project Architecture

```text
                 PORTFOLIO WEBSITE
                         │
         ┌───────────────┴───────────────┐
         │                               │
   PUBLIC WEBSITE                   ADMIN PANEL
   /                                /admin
         │                               │
   Read-only portfolio             Authenticated login
         │                               │
                                    Dashboard
         │                               │
      Hero/About/Skills/Projects     Job Roles
      Experience/Certifications        Skills
      Education/Achievements          Experience
      Contact/Resume                  Projects
                                      Certifications
                                      Education
                                      Achievements
                                      About
                                      Social Links
                                      Resume
                                      Site Settings
         │                               │
         └───────────────┬───────────────┘
                         │
                    Supabase / Prisma
                    PostgreSQL Database
```

---

## Public Website Requirements

The public website must be accessible without login and should include:

- Navbar with responsive mobile menu
- Home/Hero section
- About section
- Skills section
- Experience timeline or cards
- Projects section
- Certifications section
- Education section
- Achievements section
- Resume download button
- Contact section
- Footer
- Light/Dark/System theme switch

The public site must be responsive, professional, and professional enough for job applications and recruiter review.

---

## Homepage Content

The homepage should present:

- name
- professional title
- short introduction
- profile picture
- CTA buttons
- social links
- current job role or focus area

Examples:

```text
Hi, I'm Jahnavi
Software / Automation Engineer
I build reliable automation, test APIs, and work with Python, networking technologies, and engineering tools.
```

Do not hardcode critical portfolio information in the frontend if it is meant to be editable via admin.

---

## Dynamic Job Role System

This is one of the most important features.

Create a `JobRole` database model with fields like:

- id
- title
- shortDescription
- description
- displayOrder
- isActive
- createdAt
- updatedAt

Example values:

- Automation Engineer
- Software Engineer
- QA Automation Engineer
- Python Developer
- Network Automation Engineer

Admin should be able to:

- add a job role
- edit a job role
- delete a job role
- reorder roles
- activate/deactivate roles
- select a current primary role

The public page should automatically display the currently active role.

---

## Dynamic Skills System

Create a `Skill` model with fields such as:

- id
- name
- category
- description
- icon
- proficiencyLevel
- displayOrder
- isActive
- createdAt
- updatedAt

Example categories:

- Programming
- Testing & Automation
- API & Web Services
- Networking
- Databases
- DevOps & Tools
- Core Engineering

Example skills:

- Python
- Java
- SQL
- Git
- GitHub
- Jenkins
- CI/CD
- REST APIs
- Postman
- PyATS
- Pytest
- Playwright
- Selenium
- Linux
- MySQL
- PostgreSQL

Admin functionality:

- add
- edit
- delete
- reorder
- category change
- active/inactive toggle

---

## Experience System

Create an `Experience` model with fields like:

- id
- company
- position
- location
- employmentType
- startDate
- endDate
- isCurrent
- description
- displayOrder
- isActive
- createdAt
- updatedAt

Each experience should allow bullet points.

Example:

```text
Cisco Systems India Pvt Ltd
Automation Trainee
Bengaluru, India
Oct 2025 – Apr 2026

• Built Python automation for device connectivity checks.
• Tested REST APIs using Postman and automation scripts.
• Automated regression scenarios.
• Troubleshot multi-service failures through log analysis.
```

Admin should be able to:

- add experience
- edit details
- remove bullet points
- mark current position
- reorder experience items
- toggle active/inactive

---

## Projects System

Create a `Project` model with fields like:

- id
- title
- shortDescription
- description
- technologies
- githubUrl
- liveUrl
- imageUrl
- displayOrder
- featured
- isActive
- createdAt
- updatedAt

Example project:

```text
CNC ICMP Reachability Automation
```

Technologies may include:

- Python
- pyATS
- REST APIs
- Postman
- Automation
- Networking

Admin can:

- add project
- edit project
- delete project
- feature/unfeature project
- reorder projects
- add GitHub URL
- add live URL
- upload image

Public website should show projects in professional cards.

---

## Certifications System

Create a `Certification` model with fields like:

- id
- name
- issuer
- issueDate
- expirationDate
- credentialId
- credentialUrl
- imageUrl
- description
- displayOrder
- isActive

Admin can:

- add certification
- edit certification
- delete certification
- add credential URL
- upload certificate image
- reorder certifications

---

## Education System

Create an `Education` model with fields like:

- id
- institution
- degree
- fieldOfStudy
- location
- startDate
- endDate
- grade
- description
- displayOrder
- isActive

Example:

```text
Vignan's University
B.Tech in Electronics and Communication Engineering
2021 – 2025
CGPA: 8.01/10
```

---

## Achievements System

Create an `Achievement` model with fields like:

- id
- title
- description
- date
- organization
- link
- imageUrl
- displayOrder
- isActive

Admin can manage achievements with full CRUD support.

---

## About Me Section

The About section should be editable from the admin panel.

Admin should manage:

- heading
- short biography
- full biography
- current focus
- career objective
- profile image

This text should not be hardcoded permanently in the frontend.

---

## Social Links

Create a dynamic `SocialLink` system.

Examples:

- GitHub
- LinkedIn
- Email
- Project portfolio links

Admin can:

- add social links
- edit social links
- delete social links
- reorder links
- enable/disable links
- validate URL format

---

## Resume Management

Admin must be able to upload and replace the resume.

Requirements:

- PDF upload
- update existing resume
- public download button
- stored safely in Supabase Storage
- filtered by file type and validated server-side

The public website should include a clean Download Resume button.

---

## Admin Authentication

Create a protected admin system under `/admin`.

Use Supabase Auth.

The login flow should be:

```text
/admin
   ↓
login form
   ↓
Supabase Auth
   ↓
Authenticated admin session
   ↓
/admin/dashboard
```

Important rules:

- never implement password checks in frontend code
- do not store admin credentials in client-side files
- unauthenticated users must be redirected away from admin pages
- public users must not have access to admin actions

---

## Admin Dashboard

Create a professional dashboard with a sidebar and content cards.

Example sidebar items:

- Dashboard
- Job Roles
- Skills
- Experience
- Projects
- Certifications
- Education
- Achievements
- About
- Social Links
- Resume
- Site Settings

Dashboard summary cards should display counts such as:

- Job Roles
- Skills
- Experience
- Projects
- Certifications
- Education
- Achievements

---

## CRUD Admin Experience

Every admin section should support CRUD operations.

Example table layout:

```text
Skills

[+ Add Skill]

Name        Category        Status     Actions
Python      Programming     Active     Edit Delete
PyATS       Automation      Active     Edit Delete
SQL         Database        Active     Edit Delete
```

Use shadcn UI components for:

- Dialog
- Button
- Input
- Textarea
- Select
- Checkbox
- Switch
- Dropdown Menu
- Table
- Card
- Toast
- Alert Dialog

For destructive actions, always show a confirmation dialog before deleting data.

---

## Reordering and Active Status

Order matters for many sections, including:

- job roles
- skills
- experience
- projects
- certifications
- education
- achievements

Every item should support:

- active
- inactive

Inactive items should not appear publicly until activated.

---

## Featured Projects

Projects should support a `featured` flag.

Featured projects should appear prominently on the homepage or a dedicated featured section.

---

## Site Settings

Create a `SiteSettings` model for:

- name
- professional title
- email
- phone
- location
- short intro
- footer text
- GitHub URL
- LinkedIn URL
- resume URL
- SEO title
- SEO description
- profile image
- favicon

---

## Theme System

Implement a proper theme system using `next-themes`.

Supported modes:

- Light
- Dark
- System

The theme should apply across:

- public portfolio
- admin dashboard
- login page
- forms
- cards
- tables
- navbars
- footer
- dialogs

Persist user preference.

---

## Design Direction

The design should feel modern, engineering-focused, and professional.

Recommended style characteristics:

- clean typography
- generous spacing
- subtle animations
- clear hierarchy
- strong contrast
- premium portfolio appearance
- not over-designed or cluttered
- consistent border radius and card layout

Avoid:

- excessive gradients
- heavy template feel
- low contrast text
- overdone animations
- generic-looking UI

---

## Animations and UX

Use subtle motion such as:

- fade-in sections
- hover effects on cards
- smooth scrolling
- button transitions
- navbar transitions

Respect reduced motion preferences with `prefers-reduced-motion` support.

---

## Responsive Design

The complete site must work well on:

- mobile
- tablet
- laptop
- desktop

Admin dashboard must also be responsive.

On small screens:

- sidebar becomes a drawer
- forms stack vertically
- tables must remain readable
- buttons remain touch-friendly

---

## SEO and Metadata

Add:

- page titles
- meta descriptions
- Open Graph metadata
- Twitter/X metadata
- robots.txt
- sitemap
- canonical URLs
- semantic HTML structure

This will improve discoverability and professional presentation.

---

## Accessibility

Follow accessibility best practices.

Ensure:

- keyboard navigation works
- focus states are visible
- labels are present on form fields
- contrast is readable
- buttons and dialogs are accessible
- alt text exists for images
- semantic HTML is used
- screen-reader friendly content

---

## Performance

Optimize for speed by using:

- Server Components by default
- optimized images
- lazy loading where useful
- minimal client-side JavaScript
- efficient Prisma queries
- caching and revalidation where appropriate
- optimized fonts

Keep the homepage fast and smooth.

---

## Security Requirements

This is critical.

Implement:

- Supabase Auth
- server-side authorization checks
- protected admin routes
- database row-level security where appropriate
- Zod validation for all input
- server-side validation before mutation
- secure file upload handling
- URL validation
- no secrets in frontend code
- environment-based configuration

Never trust the client for permissions.

---

## Database Design

A proper Prisma schema should include models like:

```prisma
model JobRole {
  id            String   @id @default(cuid())
  title         String
  shortDescription String?
  description   String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Skill {
  id            String   @id @default(cuid())
  name          String
  category      String
  description   String?
  icon          String?
  proficiencyLevel String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Experience {
  id            String   @id @default(cuid())
  company       String
  position      String
  location      String?
  employmentType String?
  startDate     DateTime?
  endDate       DateTime?
  isCurrent     Boolean  @default(false)
  description   String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Project {
  id            String   @id @default(cuid())
  title         String
  shortDescription String?
  description   String?
  technologies  String[]
  githubUrl     String?
  liveUrl       String?
  imageUrl      String?
  displayOrder  Int
  featured      Boolean  @default(false)
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Certification {
  id            String   @id @default(cuid())
  name          String
  issuer        String?
  issueDate     DateTime?
  expirationDate DateTime?
  credentialId  String?
  credentialUrl String?
  imageUrl      String?
  description   String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Education {
  id            String   @id @default(cuid())
  institution   String
  degree        String
  fieldOfStudy  String?
  location      String?
  startDate     DateTime?
  endDate       DateTime?
  grade         String?
  description   String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model Achievement {
  id            String   @id @default(cuid())
  title         String
  description   String?
  date          DateTime?
  organization  String?
  link          String?
  imageUrl      String?
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model SocialLink {
  id            String   @id @default(cuid())
  platform      String
  url           String
  displayOrder  Int
  isActive      Boolean  @default(true)
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

model SiteSettings {
  id            String   @id @default(cuid())
  name          String
  professionalTitle String?
  email         String?
  phone         String?
  location      String?
  shortIntro    String?
  footerText    String?
  githubUrl     String?
  linkedinUrl   String?
  resumeUrl     String?
  seoTitle      String?
  seoDescription String?
  profileImageUrl String?
  faviconUrl    String?
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}
```

---

## Project Structure

```text
portfolio/
├── app/
│   ├── (public)/
│   │   ├── page.tsx
│   │   ├── about/
│   │   ├── projects/
│   │   ├── experience/
│   │   ├── certifications/
│   │   ├── contact/
│   │   └── layout.tsx
│   ├── admin/
│   │   ├── login/
│   │   ├── dashboard/
│   │   ├── jobs/
│   │   ├── skills/
│   │   ├── experience/
│   │   ├── projects/
│   │   ├── certifications/
│   │   ├── education/
│   │   ├── achievements/
│   │   ├── about/
│   │   ├── social-links/
│   │   ├── resume/
│   │   └── settings/
│   ├── globals.css
│   ├── layout.tsx
│   └── not-found.tsx
├── components/
│   ├── navbar/
│   ├── footer/
│   ├── hero/
│   ├── about-section/
│   ├── skills-section/
│   ├── experience-section/
│   ├── projects-section/
│   ├── certifications-section/
│   ├── education-section/
│   ├── achievements-section/
│   ├── contact-section/
│   ├── theme-toggle/
│   ├── admin/
│   └── ui/
├── lib/
│   ├── prisma.ts
│   ├── supabase.ts
│   ├── auth.ts
│   ├── utils.ts
│   └── data.ts
├── prisma/
│   ├── schema.prisma
│   └── seed.ts
├── public/
│   ├── images/
│   ├── icons/
│   └── resume/
├── actions/
│   ├── job-role.ts
│   ├── skill.ts
│   ├── experience.ts
│   ├── project.ts
│   ├── certification.ts
│   ├── education.ts
│   ├── achievement.ts
│   ├── social-link.ts
│   └── site-settings.ts
├── schemas/
│   ├── job-role.ts
│   ├── skill.ts
│   ├── project.ts
│   └── site-settings.ts
├── types/
│   └── index.ts
├── hooks/
│   └── use-theme.ts
├── middleware.ts
├── next.config.js
├── tailwind.config.ts
├── tsconfig.json
├── .env.example
├── .gitignore
├── package.json
├── README.md
└── vercel.json
```

---

## Route Structure

```text
/
/about
/projects
/experience
/certifications
/contact

/admin
/admin/login
/admin/dashboard
/admin/jobs
/admin/skills
/admin/experience
/admin/projects
/admin/certifications
/admin/education
/admin/achievements
/admin/about
/admin/social-links
/admin/resume
/admin/settings
```

---

## Environment Variables

Create a `.env.local` file and include values like:

```env
DATABASE_URL="postgresql://..."
DIRECT_URL="postgresql://..."

NEXT_PUBLIC_SUPABASE_URL="https://..."
NEXT_PUBLIC_SUPABASE_ANON_KEY="..."
SUPABASE_SERVICE_ROLE_KEY="..."
NEXT_PUBLIC_SITE_URL="http://localhost:3000"
```

Create `.env.example` with placeholders and never commit the real `.env` file.

---

## Local Development Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Generate Prisma client

```bash
npx prisma generate
```

### 3. Run Prisma migrations

```bash
npx prisma migrate dev --name init
```

### 4. Start the app locally

```bash
npm run dev
```

### 5. Production build

```bash
npm run build
npm run start
```

---

## Seed Data

Create initial sample content using Prisma seed.

Seed data should include:

- several skills
- at least 2 experience entries
- multiple projects
- certifications
- education
- achievements
- social links
- site settings

This makes the site usable immediately and gives a realistic baseline for the portfolio.

---

## Authentication Setup

### Supabase Auth

1. Create a Supabase project.
2. Enable email authentication.
3. Create a table or auth-based user flow for admin access.
4. Use protected admin routes.
5. Add server-side checks for all admin mutations.

Admin must be protected by server-side checks, not only frontend conditions.

---

## Security Model

Public users:

- read published/active content only

Admin users:

- create
- read
- update
- delete
- reorder
- activate/deactivate
- upload files

Never trust the browser for authorization.

---

## Admin CRUD Rules

Each content type should have:

- add form
- edit form
- delete action
- list view
- sort/order capability
- active/inactive toggle
- empty state
- validation
- loading state
- success/error feedback

Use React Hook Form + Zod to validate all data before saving.

---

## Search and Filtering

Add search/filter for sections where useful.

Examples:

- skills: search by name and filter by category
- projects: search by title and filter featured status
- experience: search by company or position
- certifications: search by name or issuer

---

## Error Handling and Validation

Implement friendly messages for:

- invalid form input
- failed DB operation
- failed upload
- unauthorized access
- server issues

Do not expose raw database errors to users.

---

## Testing Strategy

Add tests for the most critical functionality:

- admin authentication
- route protection
- CRUD actions
- public page rendering
- validation
- resume upload
- theme switching

At minimum, test:

- role-based access
- invalid inputs
- successful create/update/delete flows

---

## Deployment Plan

Deploy to Vercel.

Pre-deployment checklist:

- production build succeeds
- Supabase variables configured
- Prisma connection works
- admin authentication works in production
- upload storage works
- public pages load with dynamic data
- SEO metadata works
- no secret leakage in client code

---

## Development Roadmap

### Phase 1: Project Setup

- initialize Next.js app
- configure TypeScript, Tailwind, ESLint, Prettier
- install Prisma and Supabase packages
- configure shadcn/ui

### Phase 2: Public Portfolio Layout

- build navbar
- build hero
- build about
- build skills
- build experience
- build projects
- build certifications
- build education
- build achievements
- build contact
- build footer

### Phase 3: Theme Setup

- add Light/Dark/System theme
- ensure accessibility and contrast
- test across all components

### Phase 4: Database and Supabase

- create Supabase project
- create PostgreSQL tables
- configure Prisma schema
- run migrations

### Phase 5: Admin Authentication

- create admin login page
- protect admin routes
- verify access rules

### Phase 6: Admin Dashboard and CRUD

- dashboard overview cards
- implement job roles CRUD
- implement skills CRUD
- implement experience CRUD
- implement projects CRUD
- implement certifications CRUD
- implement education CRUD
- implement achievements CRUD
- implement about/social/resume/settings CRUD

### Phase 7: Connect Data to Public Pages

- replace mock data with database queries
- add loading and empty states
- revalidate pages after admin updates

### Phase 8: Security and Polish

- enforce auth and permissions
- add validation
- improve accessibility
- improve responsiveness
- optimize performance

### Phase 9: Final Testing and Deployment

- run build
- test admin flows
- test public pages
- deploy to Vercel

---

## Final Acceptance Criteria

The project is complete only when all of the following work:

### Public features

- homepage renders correctly
- about section works
- skills display dynamically
- experience displays correctly
- projects display correctly
- certifications show properly
- education is visible
- achievements are visible
- contact information is available
- resume download works
- social links work
- dark mode and light mode work
- site is responsive
- SEO metadata is in place

### Admin features

- admin login works
- unauthorized user cannot access protected routes
- dashboard loads correctly
- job roles CRUD works
- skills CRUD works
- experience CRUD works
- projects CRUD works
- certifications CRUD works
- education CRUD works
- achievements CRUD works
- about editing works
- social links editing works
- resume upload works
- site settings update works
- reordering works
- active/inactive controls work
- confirmation dialogs work

### Security

- admin routes are protected server-side
- public users cannot edit data
- secrets are stored in environment variables
- file uploads are validated
- no hardcoded passwords or API keys

### Deployment

- production build succeeds
- Vercel deployment works
- environment variables are documented
- README is complete and clear

---

## Design Goal

The final portfolio should feel like a premium engineering portfolio, not a generic template.

It should communicate:

- professional
- technical
- modern
- reliable
- engineering-focused
- credible for recruiters and employers

---

## Final Recommendation

Build this site incrementally and verify each stage before moving to the next one.

Do not start by building everything at once. Instead:

1. create the app shell
2. build the public portfolio UI
3. add database and auth
4. build the admin dashboard
5. connect the frontend to the database
6. secure admin routes
7. test everything
8. deploy

This approach keeps the project maintainable, easier to debug, and aligned with the goal of a strong portfolio CMS.

---

## Quick Start

```bash
npm install
npx prisma generate
npx prisma migrate dev
npm run dev
```

Then open:

- Local app: http://localhost:3000
- Admin login: http://localhost:3000/admin/login

---

## Summary

This portfolio website is not just a personal site; it is a dynamic content management system for a professional identity.

The public site shows the portfolio, while the admin area allows the owner to manage everything safely and without touching source code.

That makes the project scalable, maintainable, and suitable for long-term professional use.


---

## Development Roadmap

### Phase 1: Initial Setup
- Create the Next.js app
- Install TypeScript, Tailwind, Prisma, Supabase SDK, shadcn/ui
- Configure project folders
- Set up linting and formatting

### Phase 2: Public Portfolio Layout
- Build navbar
- Build hero section
- Build about section
- Build skills section
- Build experience section
- Build projects section
- Build certifications section
- Build education and achievements
- Build contact section
- Build footer

### Phase 3: Theme System
- Add dark mode/light mode toggle
- Use `next-themes`
- Make sure text, cards, buttons, forms, tables, and admin UI all adapt correctly

### Phase 4: Database Setup
- Create Supabase project
- Connect PostgreSQL database
- Set up Prisma schema
- Run migrations

### Phase 5: Authentication
- Set up Supabase Auth
- Protect admin routes
- Add login page
- Add logout flow

### Phase 6: Admin Dashboard
- Add dashboard overview cards
- Create CRUD pages for each section
- Validate form inputs
- Add edit and delete actions

### Phase 7: Connect Frontend to Database
- Replace mock data with database queries
- Display dynamic data on the public portfolio
- Add loading and empty states

### Phase 8: Security and RLS
- Set access rules for public and admin data
- Prevent unauthorized edits through API routes
- Test login and access behavior

### Phase 9: Polish
- Responsive layout
- Animations
- SEO metadata
- Favicon
- Resume download
- Error/empty states
- Accessibility fixes

### Phase 10: Deployment
- Push to GitHub
- Deploy to Vercel
- Configure environment variables
- Point custom domain if required

---

## Recommended Build Order

1. Next.js foundation
2. Portfolio UI
3. Dark/light theme
4. Supabase + Prisma setup
5. Authentication
6. Admin dashboard
7. CRUD pages
8. Connect database to UI
9. Security and RLS
10. Deployment

---

## Suggested First Version

Start with a simple working site before adding advanced features.

Build first:
- home page
- about section
- skills section
- projects section
- experience section
- admin login
- one CRUD area like skills

Only after that, expand to the rest of the portfolio.

---

## Environment Variables

Example:

```env
NEXT_PUBLIC_SUPABASE_URL=your_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
DATABASE_URL=your_postgres_connection_string
NEXTAUTH_SECRET=your_secret
```

---

## Local Development Commands

```bash
npm install
npm run dev
```

Production build:

```bash
npm run build
npm run start
```

---

## Final Recommendation

This portfolio should be built as a dynamic content system, not a static one-page site. The public side should read from the database, while the admin side should manage it.

That makes the site easier to maintain and much more professional for future job applications, projects, and updates.

---

## Next Step

The next step is to initialize the project scaffold using Next.js, then create:
- project folder
- Tailwind setup
- database config
- admin login screen
- first public page

Once that is complete, the rest of the portfolio sections can be added in order.
