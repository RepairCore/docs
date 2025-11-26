# Installation

This guide will walk you through installing RepairCore on your server or local development environment.

## Prerequisites

Before you begin, ensure you have met the [System Requirements](system-requirements.md).

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/repaircore.git
cd repaircore/repair-core
```

### 2. Install PHP Dependencies

```bash
composer install
```

### 3. Install Node Dependencies

```bash
# Install admin theme dependencies
cd ../public_html/themes/admin
npm install

# Install frontend theme dependencies
cd ../frontend
npm install
```

### 4. Configure Environment

```bash
cd ../../../repair-core
cp .env.example .env
php artisan key:generate
```

### 5. Configure Database

Edit the `.env` file with your database credentials:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=repaircore
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

### 6. Run Migrations

```bash
php artisan migrate
```

### 7. Seed Demo Data (Optional)

```bash
php artisan db:seed
```

### 8. Build Frontend Assets

```bash
# Build admin theme
cd ../public_html/themes/admin
npm run build

# Build frontend theme
cd ../frontend
npm run build
```

### 9. Start Development Server

```bash
cd ../../../repair-core
php artisan serve
```

Visit `http://localhost:8000` to access the application.

## Quick Setup Script

Alternatively, use the built-in setup script:

```bash
composer setup
```

This will automatically:
- Install all dependencies
- Generate application key
- Run migrations
- Build assets

## Development Mode

For active development with hot reloading:

```bash
composer dev
```

This starts:
- PHP development server
- Queue worker
- Log viewer (Pail)
- Vite dev server with HMR

## Troubleshooting

### Permission Issues

If you encounter permission errors:

```bash
chmod -R 755 storage bootstrap/cache
```

### Database Connection Failed

- Verify database credentials in `.env`
- Ensure database server is running
- Check database user has proper permissions

### Asset Build Errors

- Clear npm cache: `npm cache clean --force`
- Delete `node_modules` and reinstall: `rm -rf node_modules && npm install`

---

Next: [Configuration](configuration.md)
