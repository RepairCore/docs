# Database Design

Understanding RepairCore's database schema and design principles.

## Design Principles

### Standard Columns

All tables include:
- `id` - Primary key (auto-increment)
- `created_at` - Creation timestamp
- `updated_at` - Last update timestamp
- `deleted_at` - Soft delete timestamp (nullable)
- `createdBy` - User ID who created the record
- `updatedBy` - User ID who last updated the record

### Design Guidelines

**No Foreign Keys**
- Flexible schema without rigid constraints
- Easier migrations and modifications

**Nullable Columns**
- Most columns are nullable for flexible data entry
- Required fields enforced at application level

**Status Management**
- Status columns use VARCHAR (string)
- Default value: "draft"
- Common statuses: draft, pending, active, completed, cancelled

**Slug Support**
- SEO-friendly URLs
- Automatic generation via `HasSlug` trait
- Unique constraint on slug columns

**Meta Tables**
- Flexible custom fields via metadata pattern
- Key-value storage for extensibility

## Core Tables

### Users & Authentication

**users**
- User accounts (customers, staff, admins)
- Authentication credentials
- Profile information

**roles**
- Role definitions
- Permission assignments

**social_accounts**
- OAuth provider links
- Social login data

**user_meta**
- Custom user fields
- Flexible metadata

### Repair Management

**repair_orders**
- Main repair order entity
- Customer and device information
- Status tracking
- Financial data

**repair_items**
- Individual repair line items
- Services and parts
- Pricing

**repair_order_assignments**
- Technician assignments
- Workload distribution

**repair_progress_logs**
- Detailed activity timeline
- Status changes
- Notes and photos

**repair_order_meta**
- Custom order fields

**repair_item_meta**
- Custom item fields

### Inventory

**parts**
- Parts catalog
- SKU management
- Stock levels
- Pricing

**part_brands**
- Brand management

**part_categories**
- Hierarchical categorization
- Parent-child relationships

### Services

**services**
- Service definitions
- Descriptions and pricing
- Duration estimates

**service_categories**
- Service categorization

### Devices

**devices**
- Device catalog
- Make, model, specifications
- Serial numbers

### Financial

**tax_classes**
- Tax rate definitions
- Tax calculation rules

### Content

**posts**
- Blog posts
- Content pages

**categories**
- Post categories

**tags**
- Post tags

**media**
- File storage
- Media metadata

**media_folders**
- Folder structure

### System

**settings**
- Application settings
- Key-value storage

**labels**
- Custom labels
- Workflow indicators

**notification_templates**
- Email/SMS templates

**notification_preferences**
- User notification settings

## Relationships

### One-to-Many

- User → RepairOrders
- RepairOrder → RepairItems
- RepairOrder → RepairProgressLogs
- Category → Posts
- PartBrand → Parts

### Many-to-Many

- RepairOrder ↔ Labels
- Post ↔ Tags
- User ↔ Roles

### Polymorphic

- Media (attachable to multiple models)
- Meta tables (for flexible custom fields)

## Indexing Strategy

### Primary Indexes

- All tables have primary key on `id`

### Foreign Key Indexes

- User IDs (createdBy, updatedBy)
- Relationship columns

### Unique Indexes

- Slugs
- Email addresses
- SKU codes

### Full-Text Indexes

- Post content
- Part descriptions
- Service descriptions

## Migration Strategy

### Version Control

All schema changes are version-controlled through migrations.

### Rollback Support

Each migration includes `up()` and `down()` methods for rollback capability.

### Seeder Support

Demo data available through seeders for testing.

---

Next: [Security Features](security.md)
