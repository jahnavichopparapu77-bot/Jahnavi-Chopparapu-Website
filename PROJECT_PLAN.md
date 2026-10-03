# Portfolio Website Project Plan

This file tracks the build progress for the Jahnavi Chopparapu portfolio website. Each phase is broken down into clear tasks and can be marked complete as work is finished.

## Status Legend

- [ ] Not started
- [ ] In progress
- [x] Completed

---

## Phase 1: Project Setup

### Goals
- Create the project foundation
- Set up Next.js, TypeScript, Tailwind, and supporting tools
- Prepare the repository structure

### Tasks
- [ ] Initialize Next.js app with App Router
- [ ] Configure TypeScript
- [ ] Configure Tailwind CSS
- [ ] Add ESLint and Prettier
- [ ] Install shadcn/ui
- [ ] Install Lucide React
- [ ] Install Prisma
- [ ] Install Supabase SDK
- [ ] Install Zod and React Hook Form
- [ ] Set up project folders
- [ ] Create Git repo and branch strategy
- [ ] Add .gitignore and .env.example

### Notes
- Keep the project clean and production-ready from the start.
- Avoid overbuilding before the public UI is created.

---

## Phase 2: Public Portfolio UI

### Goals
- Build the public portfolio layout
- Create all main sections for the portfolio website

### Tasks
- [ ] Build overall app layout and global styles
- [ ] Create responsive navbar
- [ ] Build hero section
- [ ] Build About section
- [ ] Build Skills section
- [ ] Build Experience section
- [ ] Build Projects section
- [ ] Build Certifications section
- [ ] Build Education section
- [ ] Build Achievements section
- [ ] Build Contact section
- [ ] Build footer
- [ ] Add CTA buttons and resume button
- [ ] Add responsive mobile navigation
- [ ] Integrate smooth scrolling and clean section spacing

### Notes
- Use temporary demo data first.
- Keep layout professional and recruiter-friendly.

---

## Phase 3: Theme System

### Goals
- Add light/dark/system theme support
- Make the portfolio visually consistent across pages

### Tasks
- [ ] Install next-themes
- [ ] Configure theme provider
- [ ] Add theme toggle button
- [ ] Apply theme variables to app
- [ ] Update public pages for dark/light compatibility
- [ ] Update admin pages for dark/light compatibility
- [ ] Ensure contrast and accessibility are maintained
- [ ] Test theme persistence locally

### Notes
- Validate contrast for text, cards, tables, and forms.

---

## Phase 4: Supabase and Database Setup

### Goals
- Create backend data layer
- Connect Prisma to Supabase PostgreSQL

### Tasks
- [ ] Create Supabase project
- [ ] Create PostgreSQL database
- [ ] Add environment variables
- [ ] Configure Prisma connection
- [ ] Create Prisma schema
- [ ] Add schema models for:
  - [ ] JobRole
  - [ ] Skill
  - [ ] Experience
  - [ ] Project
  - [ ] Certification
  - [ ] Education
  - [ ] Achievement
  - [ ] SocialLink
  - [ ] SiteSettings
- [ ] Run Prisma migrations
- [ ] Generate Prisma client
- [ ] Test database connection

### Notes
- Make sure the database is ready before connecting public pages.

---

## Phase 5: Seed Data

### Goals
- Have realistic sample data for development
- Make the site usable immediately after setup

### Tasks
- [ ] Create seed script
- [ ] Add sample job roles
- [ ] Add sample skills
- [ ] Add sample experience entries
- [ ] Add sample projects
- [ ] Add sample certifications
- [ ] Add sample education data
- [ ] Add sample achievements
- [ ] Add sample site settings
- [ ] Add sample social links
- [ ] Run seed script successfully

### Notes
- Seed data should be realistic and replaceable later.

---

## Phase 6: Admin Authentication

### Goals
- Secure the admin area
- Allow only authenticated admin users to access the dashboard

### Tasks
- [ ] Configure Supabase Auth
- [ ] Create admin login page
- [ ] Add login form UI
- [ ] Add login server action or auth flow
- [ ] Protect admin routes
- [ ] Redirect unauthenticated users to login
- [ ] Add logout flow
- [ ] Secure admin routes with server-side checks
- [ ] Test login and logout flow

### Notes
- Do not rely only on frontend checks for access control.

---

## Phase 7: Admin Dashboard

### Goals
- Create the management interface for content updates
- Build dashboard overview and navigation

### Tasks
- [ ] Create admin layout
- [ ] Create admin sidebar
- [ ] Create admin header/navbar
- [ ] Create dashboard summary cards
- [ ] Add metrics for counts of:
  - [ ] Job Roles
  - [ ] Skills
  - [ ] Experience
  - [ ] Projects
  - [ ] Certifications
  - [ ] Education
  - [ ] Achievements
- [ ] Add dashboard empty/loading states
- [ ] Add navigation links for all admin sections

### Notes
- The dashboard should feel like a mini CMS.

---

## Phase 8: Job Role Management

### Goals
- Allow dynamic management of job roles

### Tasks
- [ ] Create Job Role list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Validate data with Zod
- [ ] Save to database
- [ ] Display on public page from database
- [ ] Test create/edit/delete flow

### Notes
- This is one of the highest-priority pieces.

---

## Phase 9: Skills Management

### Goals
- Manage portfolio skills from admin without code changes

### Tasks
- [ ] Create Skills list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add category selection
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Validate input
- [ ] Save to database
- [ ] Display skills on public page
- [ ] Test CRUD flow

### Notes
- Keep skills grouped logically by category.

---

## Phase 10: Experience Management

### Goals
- Allow full experience CRUD and timeline updates

### Tasks
- [ ] Create Experience list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add bullet list support
- [ ] Add current position toggle
- [ ] Add date validation
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Save to database
- [ ] Display experience on public site
- [ ] Test CRUD flow

### Notes
- Experience should render cleanly in a timeline or card layout.

---

## Phase 11: Projects Management

### Goals
- Allow full portfolio project updates from admin

### Tasks
- [ ] Create Project list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add technologies field
- [ ] Add GitHub and live URL fields
- [ ] Add image upload support
- [ ] Add featured toggle
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Save to database
- [ ] Display projects on public site
- [ ] Test CRUD flow

### Notes
- FEATURED projects should stand out on the homepage.

---

## Phase 12: Certifications Management

### Goals
- Manage certifications through the admin dashboard

### Tasks
- [ ] Create Certification list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add credential URL support
- [ ] Add certificate image support
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Save to database
- [ ] Display certifications publicly
- [ ] Test CRUD flow

### Notes
- Keep cards clean and professional.

---

## Phase 13: Education Management

### Goals
- Add and maintain academic background dynamically

### Tasks
- [ ] Create Education list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add date fields
- [ ] Add grading and description fields
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Save to database
- [ ] Display education publicly
- [ ] Test CRUD flow

### Notes
- Education data should be easy to update without editing code.

---

## Phase 14: Achievements Management

### Goals
- Allow achievements to be added and managed dynamically

### Tasks
- [ ] Create Achievements list page
- [ ] Add create form
- [ ] Add edit form
- [ ] Add delete action with confirmation
- [ ] Add date and organization fields
- [ ] Add optional link and image field
- [ ] Add reorder support
- [ ] Add active/inactive toggle
- [ ] Save to database
- [ ] Display achievements publicly
- [ ] Test CRUD flow

### Notes
- Keep this section concise and professional.

---

## Phase 15: About and Social Links

### Goals
- Make the profile and contact details editable from admin

### Tasks
- [ ] Create About management page
- [ ] Add biography editing fields
- [ ] Add profile image support
- [ ] Add career/focus editing
- [ ] Create Social Links management page
- [ ] Add create/edit/delete support
- [ ] Validate URLs
- [ ] Add ordering support
- [ ] Save to database
- [ ] Display profile and links publicly
- [ ] Test updates

### Notes
- Social links should be clean and ordered properly.

---

## Phase 16: Resume Upload and Download

### Goals
- Allow admin to upload and update the resume
- Make resume available publicly

### Tasks
- [ ] Configure Supabase Storage
- [ ] Create resume upload form
- [ ] Add PDF validation
- [ ] Upload resume file securely
- [ ] Store the file URL in database
- [ ] Add public download button
- [ ] Replace existing resume safely
- [ ] Test resume download behavior

### Notes
- Validate file type and file size before upload.

---

## Phase 17: Site Settings and SEO Metadata

### Goals
- Add site-wide settings and metadata management

### Tasks
- [ ] Create Site Settings page
- [ ] Add editable personal info
- [ ] Add contact details
- [ ] Add social URLs
- [ ] Add SEO title and description
- [ ] Add profile image and favicon fields
- [ ] Save to database
- [ ] Use settings in the public app
- [ ] Test metadata rendering

### Notes
- Site settings should power a significant portion of the portfolio.

---

## Phase 18: Public Data Integration

### Goals
- Connect public pages to the database
- Replace mock/demo data with real admin-controlled content

### Tasks
- [ ] Fetch active Job Roles from database
- [ ] Fetch active Skills from database
- [ ] Fetch Experience data from database
- [ ] Fetch Projects from database
- [ ] Fetch Certifications from database
- [ ] Fetch Education from database
- [ ] Fetch Achievements from database
- [ ] Fetch About data from database
- [ ] Fetch Social Links from database
- [ ] Fetch Site Settings from database
- [ ] Fetch resume URL from database
- [ ] Add loading states
- [ ] Add empty states
- [ ] Validate public rendering

### Notes
- Each public page should pull content dynamically once connected.

---

## Phase 19: Security Hardening

### Goals
- Protect the app from unauthorized access and invalid input

### Tasks
- [ ] Verify admin route protection
- [ ] Add server-side auth checks for all mutations
- [ ] Add Zod validation for all forms
- [ ] Validate resume uploads and URLs
- [ ] Add input sanitization where needed
- [ ] Add friendly error messages
- [ ] Add server-side logging for issues
- [ ] Test unauthorized access attempts

### Notes
- Security should be checked before deployment.

---

## Phase 20: Responsive Design and UX Polish

### Goals
- Make the app polished across devices
- Improve overall user experience

### Tasks
- [ ] Review desktop layout
- [ ] Review tablet layout
- [ ] Review mobile layout
- [ ] Fix sidebar behavior on mobile
- [ ] Fix form layout on small screens
- [ ] Improve navigation spacing and usability
- [ ] Add subtle hover effects
- [ ] Review animations
- [ ] Check scroll behavior
- [ ] Improve loading states

### Notes
- This is where the site becomes production-ready and user-friendly.

---

## Phase 21: SEO and Accessibility

### Goals
- Improve discoverability and compliance with accessibility standards

### Tasks
- [ ] Add metadata to homepage
- [ ] Add metadata to major pages
- [ ] Add Open Graph tags
- [ ] Add Twitter/X tags
- [ ] Add sitemap.xml
- [ ] Add robots.txt
- [ ] Validate semantic HTML
- [ ] Inspect keyboard navigation
- [ ] Improve focus states
- [ ] Check color contrast
- [ ] Validate alt text and labels
- [ ] Test screen-reader-friendly structure

### Notes
- SEO and accessibility are part of a strong portfolio experience.

---

## Phase 22: Testing and QA

### Goals
- Verify the app works as expected
- Catch issues before deployment

### Tasks
- [ ] Run TypeScript check
- [ ] Run ESLint
- [ ] Run build
- [ ] Test public portfolio pages
- [ ] Test admin login
- [ ] Test CRUD operations
- [ ] Test form validation
- [ ] Test theme switching
- [ ] Test responsive layout
- [ ] Test unauthorized access attempts
- [ ] Fix any errors found

### Notes
- Do not proceed to deployment until build and tests are passing.

---

## Phase 23: Deployment Preparation

### Goals
- Prepare the app for production deployment

### Tasks
- [ ] Finalize environment variables
- [ ] Verify Supabase config
- [ ] Verify Prisma production connection
- [ ] Confirm admin auth works in production
- [ ] Confirm storage upload works in production
- [ ] Validate resume download in production
- [ ] Add deployment config
- [ ] Prepare Vercel project
- [ ] Add GitHub repo and branch strategy

### Notes
- Deployment should only happen after validation passes.

---

## Phase 24: Launch and Post-Launch Check

### Goals
- Publish the site and verify live functionality

### Tasks
- [ ] Deploy to Vercel
- [ ] Check live homepage
- [ ] Check public sections
- [ ] Verify admin login
- [ ] Test CRUD from live environment
- [ ] Confirm resume download works
- [ ] Check dark/light mode
- [ ] Check metadata and page load speed
- [ ] Fix any production issues
- [ ] Final sign-off

### Notes
- This is the final validation stage before handoff.

---

## Completed Phases

Use this section to track progress.

- [x] Phase 1: Project Setup
- [ ] Phase 2: Public Portfolio UI
- [ ] Phase 3: Theme System
- [ ] Phase 4: Supabase and Database Setup
- [ ] Phase 5: Seed Data
- [ ] Phase 6: Admin Authentication
- [ ] Phase 7: Admin Dashboard
- [ ] Phase 8: Job Role Management
- [ ] Phase 9: Skills Management
- [ ] Phase 10: Experience Management
- [ ] Phase 11: Projects Management
- [ ] Phase 12: Certifications Management
- [ ] Phase 13: Education Management
- [ ] Phase 14: Achievements Management
- [ ] Phase 15: About and Social Links
- [ ] Phase 16: Resume Upload and Download
- [ ] Phase 17: Site Settings and SEO Metadata
- [ ] Phase 18: Public Data Integration
- [ ] Phase 19: Security Hardening
- [ ] Phase 20: Responsive Design and UX Polish
- [ ] Phase 21: SEO and Accessibility
- [ ] Phase 22: Testing and QA
- [ ] Phase 23: Deployment Preparation
- [ ] Phase 24: Launch and Post-Launch Check

---

## Suggested Workflow

Use this order while building:

1. Setup project and tools
2. Build public UI
3. Add theme system
4. Set up database and auth
5. Build dashboard and CRUD pages
6. Connect public pages to DB
7. Add security and validation
8. Run tests and deploy

This keeps the project structured and makes it easy to track progress.
