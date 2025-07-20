# QUICK SETUP GUIDE - Course Management System

## 🚀 Fast Setup for WAMP

### Step 1: Copy Files
```
Copy the 'backend' folder to: C:\wamp64\www\course-admin\
```

### Step 2: Database Setup
1. Start WAMP services
2. Open phpMyAdmin: `http://localhost/phpmyadmin`
3. Import your existing `admin_panel_db` or create new database
4. Use username: `root`, password: (empty)

### Step 3: Laravel Setup
```bash
cd C:\wamp64\www\course-admin
composer install
copy .env.example .env
php artisan key:generate
php artisan migrate --seed
```

### Step 4: Access Points
- **Frontend**: `http://localhost:5173` (React app)
- **Admin Panel**: `http://localhost/course-admin/public/admin`
- **Database**: `http://localhost/phpmyadmin`

### Step 5: Default Login
- **Email**: admin@example.com
- **Password**: password

## 🔧 If Links Don't Work

### Database Access Issues:
Try these URLs:
- `http://localhost/phpmyadmin`
- `http://localhost:8080/phpmyadmin`
- `http://127.0.0.1/phpmyadmin`

### Admin Panel Issues:
1. Make sure WAMP is running
2. Check if Laravel is in `www/course-admin/`
3. Try: `http://127.0.0.1/course-admin/public/admin`

## ✅ Quick Test
1. Click "Open Database" button in dashboard
2. Click "Open Admin Panel" button in dashboard
3. Both should open in new tabs

## 🆘 Emergency Fix
If nothing works:
1. Restart WAMP
2. Clear browser cache
3. Check WAMP is green (all services running)
4. Verify folder structure: `www/course-admin/public/index.php` exists