# Demo Data

Learn how to use demo data for testing and development.

## Overview

RepairCore includes seeders that populate your database with sample data for testing and demonstration purposes.

## Seeding Demo Data

### Full Database Seed

To seed all demo data:

```bash
php artisan db:seed
```

### Specific Seeders

To run specific seeders:

```bash
php artisan db:seed --class=UserSeeder
php artisan db:seed --class=RepairOrderSeeder
php artisan db:seed --class=PartSeeder
```

## What's Included

### Users

- **Admin User**
  - Email: admin@example.com
  - Password: password
  - Role: Administrator

- **Technician Users**
  - Sample technicians with various skill levels

- **Customer Users**
  - Sample customers with contact information

### Repair Orders

- Sample repair orders in various statuses
- Complete order history
- Progress logs
- Assignments

### Parts & Services

- Sample parts catalog
- Part brands and categories
- Service catalog
- Service categories

### Devices

- Sample device types
- Device brands and models

### Financial Data

- Tax classes
- Sample invoices
- Payment records

### Content

- Sample blog posts
- Categories and tags
- Media files

## Resetting Demo Data

To reset your database and reseed:

```bash
php artisan migrate:fresh --seed
```

> ⚠️ **Warning:** This will delete all existing data!

## Using Demo Data

### For Development

Demo data is useful for:
- Testing new features
- UI/UX development
- Workflow testing
- Training

### For Demonstrations

Use demo data to:
- Show potential clients
- Create screenshots
- Record tutorial videos
- Test integrations

## Customizing Seeders

You can customize seeders to match your business needs.

Seeders are located in:
```
repair-core/database/seeders/
```

### Creating Custom Seeders

```bash
php artisan make:seeder CustomSeeder
```

Edit the seeder file and run:

```bash
php artisan db:seed --class=CustomSeeder
```

## Production Warning

> ⚠️ **Never run seeders in production!**
> 
> Seeders are for development and testing only. Running them in production will create fake data in your live system.

---

Next: [Core Concepts](../core-concepts/architecture.md)
