# Course Management System - Deployment Guide

## Project Structure
```
course-management/
├── frontend/          # React TypeScript frontend
├── backend/           # Laravel + Filament backend
└── database/          # Database schema and migrations
```

## Frontend Setup (React + TypeScript)

### Development
```bash
npm install
npm run dev
```

### Production Build
```bash
npm run build
```

## Backend Setup (Laravel + Filament)

### Prerequisites
- PHP 8.1+
- Composer
- MySQL/MariaDB
- Node.js & NPM

### Installation Steps

1. **Navigate to backend directory**
```bash
cd backend
```

2. **Install PHP dependencies**
```bash
composer install
```

3. **Environment Configuration**
```bash
cp .env.example .env
```

4. **Update .env file with your database credentials**
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=admin_panel_db
DB_USERNAME=root
DB_PASSWORD=your_password
```

5. **Generate application key**
```bash
php artisan key:generate
```

6. **Run migrations and seeders**
```bash
php artisan migrate --seed
```

7. **Start development server**
```bash
php artisan serve
```

## WAMP Setup

### 1. Database Setup
- Open phpMyAdmin
- Create database `admin_panel_db` (or use your existing one)
- Import the provided SQL schema or run Laravel migrations

### 2. Laravel Setup in WAMP
1. Copy the `backend` folder to your WAMP `www` directory
2. Rename it to `course-admin` or your preferred name
3. Update `.env` file with WAMP database credentials:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=admin_panel_db
   DB_USERNAME=admin
   DB_PASSWORD=
   ```
4. Open command prompt in the project directory
5. Run: `composer install`
6. Run: `php artisan key:generate`

### 3. Access Points
- **Frontend**: `http://localhost:3000` (if using npm run dev)
- **Backend Admin**: `http://localhost/course-admin/public/admin`
- **API Endpoints**: `http://localhost/course-admin/public/api/`
- **Database Admin Panel**: `http://localhost/phpmyadmin` (Username: admin, Password: leave empty)

## Default Admin Credentials
- **Email**: admin@example.com
- **Password**: password

## Features Included

### Frontend (React)
- ✅ Course management interface
- ✅ Responsive design with Tailwind CSS
- ✅ TypeScript for type safety
- ✅ Modern component architecture

### Backend (Laravel + Filament)
- ✅ Complete admin panel with Filament
- ✅ Course CRUD operations
- ✅ Session management
- ✅ Module management
- ✅ Assessment system
- ✅ User enrollment tracking
- ✅ Role-based access control

### Database Schema
- ✅ Users table (with roles)
- ✅ Courses table
- ✅ Sessions table
- ✅ Modules table
- ✅ Assessments table
- ✅ Enrollments table
- ✅ User progress tracking

## API Endpoints

### Courses
- `GET /api/courses` - List all courses
- `POST /api/courses` - Create new course
- `GET /api/courses/{id}` - Get specific course
- `PUT /api/courses/{id}` - Update course
- `DELETE /api/courses/{id}` - Delete course

### Sessions
- `GET /api/courses/{courseId}/sessions` - List course sessions
- `POST /api/sessions` - Create new session
- `PUT /api/sessions/{id}` - Update session
- `DELETE /api/sessions/{id}` - Delete session

### Modules
- `GET /api/sessions/{sessionId}/modules` - List session modules
- `POST /api/modules` - Create new module
- `PUT /api/modules/{id}` - Update module
- `DELETE /api/modules/{id}` - Delete module

## Deployment Options

### 1. Shared Hosting
1. Upload backend files to public_html
2. Update .env with production database credentials
3. Run `composer install --no-dev`
4. Set proper file permissions

### 2. VPS/Dedicated Server
1. Set up web server (Apache/Nginx)
2. Configure PHP and database
3. Clone repository and follow installation steps
4. Set up SSL certificate
5. Configure domain/subdomain

### 3. Cloud Platforms
- **Heroku**: Use Laravel buildpack
- **DigitalOcean**: App Platform or Droplet
- **AWS**: Elastic Beanstalk or EC2
- **Vercel**: For frontend deployment

## Security Considerations
- Change default admin credentials
- Use strong database passwords
- Enable HTTPS in production
- Regular security updates
- Backup database regularly

## Troubleshooting

### Common Issues
1. **Permission errors**: Set proper file permissions (755 for directories, 644 for files)
2. **Database connection**: Verify credentials in .env file
3. **Composer errors**: Ensure PHP version compatibility
4. **Missing dependencies**: Run `composer install` and `npm install`

### Log Files
- Laravel logs: `storage/logs/laravel.log`
- Web server logs: Check Apache/Nginx error logs

## Support
For issues and questions:
1. Check Laravel documentation
2. Check Filament documentation
3. Review error logs
4. Verify environment configuration

## Next Steps
1. Customize the admin panel theme
2. Add more assessment types
3. Implement email notifications
4. Add reporting features
5. Integrate payment system (if needed)