# Configuration

Learn how to configure RepairCore for your environment.

## Environment Configuration

### Basic Settings

Edit your `.env` file to configure basic application settings:

```env
APP_NAME=RepairCore
APP_ENV=production
APP_DEBUG=false
APP_URL=https://your-domain.com
```

### Database Configuration

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=repaircore
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

### Mail Configuration

```env
MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=your_username
MAIL_PASSWORD=your_password
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=noreply@repaircore.com
MAIL_FROM_NAME="${APP_NAME}"
```

### Queue Configuration

```env
QUEUE_CONNECTION=database
```

For production, consider using Redis:

```env
QUEUE_CONNECTION=redis
REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379
```

### Cache Configuration

```env
CACHE_DRIVER=file
```

For production, use Redis:

```env
CACHE_DRIVER=redis
```

### Session Configuration

```env
SESSION_DRIVER=file
SESSION_LIFETIME=120
```

## Application Settings

### Company Information

Configure your company details in the admin panel:
- Settings > General > Company Information

### Currency Settings

Configure default currency and format:
- Settings > Financial > Currency

### Tax Settings

Set up tax classes and rates:
- Settings > Financial > Tax Classes

### Email Templates

Customize notification email templates:
- Settings > Notifications > Email Templates

### Social Login

Configure OAuth providers:
- Settings > Authentication > Social Login

See [Social Login Setup](../features/user-management/social-login.md) for details.

## File Permissions

Ensure proper permissions for storage and cache:

```bash
chmod -R 755 storage
chmod -R 755 bootstrap/cache
```

## Web Server Configuration

### Apache

Ensure `mod_rewrite` is enabled and `.htaccess` is configured.

### Nginx

See [Web Server Configuration](../deployment/web-server.md) for Nginx configuration.

## Custom Public Directory

RepairCore uses `public_html` instead of Laravel's default `public` directory.

Ensure your web server points to:
```
/path/to/repaircore/public_html
```

---

Next: [Quick Start Guide](quick-start.md)
