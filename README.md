# Admin CRUD Panel for Course Management

A comprehensive admin panel for managing online courses with hierarchical structure (Courses → Sessions → Modules → Assessments) and user enrollment system.

## Features

### Core Functionality
- **Course Management**: Full CRUD operations for courses
- **Hierarchical Structure**: Sessions within courses, modules within sessions, assessments within modules
- **User Management**: Manage system users and their roles
- **Enrollment System**: Track student enrollments and progress
- **Dashboard**: Overview with statistics and recent activity

### Design Features
- Modern, responsive design with clean UI
- Professional color scheme and typography
- Smooth animations and micro-interactions
- Mobile-friendly responsive layout
- Intuitive navigation and user experience

## Database Schema

### Tables Structure
1. **users** - System users (admins and students)
2. **courses** - Main course information
3. **sessions** - Course sections/chapters
4. **modules** - Individual learning units within sessions
5. **assessments** - Quizzes/tests for modules
6. **enrollments** - Student course enrollments
7. **user_progress** - Track individual module completion

## Setup Instructions

### Frontend Setup
1. The React application is already configured with TypeScript and Tailwind CSS
2. Run `npm run dev` to start the development server
3. The admin panel will be available at `http://localhost:5173`

### Backend Setup (WAMP)
1. Import the provided `database/schema.sql` into your MySQL database
2. Place the PHP API files from `api-examples/` into your WAMP `www` directory
3. Create a folder structure like: `www/admin-panel/api/`
4. Update database credentials in the PHP files to match your WAMP setup

### API Integration
- The frontend is configured to communicate with PHP backend at `http://localhost/admin-panel/api`
- All CRUD operations are implemented with proper error handling
- CORS is configured for cross-origin requests

## File Structure

```
src/
├── components/
│   ├── Layout/          # Sidebar and Header components
│   ├── Dashboard/       # Dashboard overview
│   ├── Courses/         # Course management components
│   ├── Users/           # User management
│   └── Enrollments/     # Enrollment tracking
├── services/            # API service layer
├── types/              # TypeScript type definitions
└── App.tsx             # Main application component

database/
└── schema.sql          # Complete database schema

api-examples/           # PHP backend examples
├── courses.php         # Course CRUD operations
└── enrollments.php     # Enrollment management
```

## Key Components

### Course Management
- **CourseList**: Display all courses with cards layout
- **CourseForm**: Create/edit course modal with validation
- **CourseDetail**: Detailed view with sessions, modules, and assessments management

### User Management
- **UserList**: Table view of all system users
- Role-based access control
- User enrollment tracking

### Enrollment System
- **EnrollmentList**: Track all student enrollments
- Progress visualization
- Status management (enrolled, in progress, completed, dropped)

## Usage

### Admin Workflow
1. **Dashboard**: View system overview and statistics
2. **Courses**: Create and manage course catalog
3. **Course Details**: Add sessions, modules, and assessments
4. **Users**: Manage system users and permissions
5. **Enrollments**: Track student progress and manage enrollments

### Course Structure
- **Course** (title, description, instructor, price, etc.)
  - **Session** (chapter/section of the course)
    - **Module** (individual learning unit with content/video)
      - **Assessment** (quiz/test for the module)

## Security Features
- Input validation on all forms
- SQL injection protection in PHP APIs
- Role-based access control
- CORS configuration for API security

## Responsive Design
- Mobile-first approach
- Optimized for desktop admin workflows
- Consistent spacing using 8px grid system
- Accessible color contrast ratios

The system provides a complete solution for managing online courses with a modern, professional interface suitable for production use.