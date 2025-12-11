# Installation

RepairCore includes a web-based installer that guides you through the setup process.

## Prerequisites

Before you begin, ensure you have met the [System Requirements](system-requirements.md).

## Installation Steps

### 1. Upload Files

Upload the RepairCore files to your web server.

### 2. Access the Installer

Navigate to your domain in a web browser. The installer will automatically start.

[image_installer_welcome]

### 3. System Check

The installer checks your server meets all requirements:
- PHP version and extensions
- Directory permissions
- Database connectivity

[image_installer_requirements]

### 4. Database Configuration

Enter your database credentials:
- Database host
- Database name
- Database username
- Database password

[image_installer_database]

### 5. Admin Account

Create your administrator account:
- Name
- Email address
- Password

[image_installer_admin]

### 6. Company Information

Enter your company details:
- Company name
- Address
- Contact information

[image_installer_company]

### 7. Complete Installation

Click **Install** to complete the setup. The installer will:
- Create database tables
- Set up default settings
- Create your admin account
- Seed demo data (optional)

[image_installer_complete]

### 8. Access Admin Panel

After installation, log in to the admin panel with your credentials.

[image_admin_login]

## Post-Installation

### Configure Email

Go to **Settings > Email** to configure SMTP for sending notifications.

### Review Settings

Check all settings pages to customize RepairCore for your business.

### Add Staff

Create user accounts for your team members.

## Troubleshooting

### Installer Not Loading

- Check file permissions
- Verify web server configuration
- Check PHP version

### Database Connection Failed

- Verify database credentials
- Ensure database server is running
- Check database user has proper permissions

### Permission Errors

Ensure these directories are writable:
- `storage/`
- `bootstrap/cache/`

---

Next: [Quick Start Guide](quick-start.md)
