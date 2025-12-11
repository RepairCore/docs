# Project Structure

Understanding RepairCore's directory structure and organization.

## Root Directory Structure

```
repaircore/
├── repair-core/          # Laravel application
├── public_html/          # Web root (custom public directory)
└── docs/                 # Documentation
```

## Laravel Application Structure

```
repair-core/
├── app/
│   ├── Console/          # Artisan commands
│   ├── Exceptions/       # Exception handlers
│   ├── Helpers/          # Helper classes
│   ├── Http/
│   │   ├── Controllers/  # Controllers
│   │   │   ├── Admin/   # Admin controllers
│   │   │   └── Api/     # API controllers
│   │   ├── Livewire/    # Livewire components
│   │   │   ├── Admin/   # Admin Livewire components
│   │   │   └── Frontend/ # Frontend Livewire components
│   │   └── Middleware/  # Custom middleware
│   ├── Models/          # Eloquent models
│   ├── Providers/       # Service providers
│   └── Traits/          # Reusable traits
├── bootstrap/           # Bootstrap files
├── config/              # Configuration files
├── database/
│   ├── factories/       # Model factories
│   ├── migrations/      # Database migrations
│   └── seeders/         # Database seeders
├── resources/
│   ├── css/            # CSS source files
│   ├── js/             # JavaScript source files
│   ├── lang/           # Language files
│   └── views/          # Blade templates
│       ├── admin/      # Admin views
│       ├── frontend/   # Frontend views
│       └── livewire/   # Livewire views
├── routes/
│   ├── web.php         # Web routes
│   ├── api.php         # API routes
│   └── console.php     # Console routes
├── storage/
│   ├── app/            # Application storage
│   ├── framework/      # Framework storage
│   └── logs/           # Log files
├── tests/              # Test files
│   ├── Feature/        # Feature tests
│   └── Unit/           # Unit tests
├── .env.example        # Environment example
├── artisan             # Artisan CLI
├── composer.json       # PHP dependencies
└── package.json        # Node dependencies
```

## Public Directory Structure

```
public_html/
├── themes/
│   ├── admin/          # Admin theme
│   │   ├── css/       # Compiled CSS
│   │   ├── js/        # Compiled JS
│   │   ├── images/    # Images
│   │   ├── fonts/     # Fonts
│   │   ├── src/       # Source files
│   │   │   ├── css/  # SCSS source
│   │   │   └── js/   # JS source
│   │   ├── package.json
│   │   └── vite.config.js
│   └── frontend/       # Frontend theme
│       ├── css/       # Compiled CSS
│       ├── js/        # Compiled JS
│       ├── images/    # Images
│       ├── src/       # Source files
│       ├── package.json
│       └── vite.config.js
├── uploads/            # User uploads
├── .htaccess          # Apache configuration
└── index.php          # Entry point
```

## Key Directories Explained

### `/app/Http/Controllers`

Controllers handle HTTP requests and return responses.

**Admin Controllers** (`/Admin`)
- Manage admin panel functionality
- Check permissions
- Use FormHelper for forms

**API Controllers** (`/Api`)
- RESTful API endpoints
- JSON responses
- API authentication

### `/app/Http/Livewire`

Livewire components for reactive UI.

**Namespace:** `App\Http\Livewire\` (NOT the default `App\Livewire\`)

**Component Folders:**
- `Device/` - Device-related components
- `Frontend/` - Customer-facing full-page components
- `Installer/` - Installation wizard
- `Part/` - Part management (backorders, etc.)
- `RepairOrder/` - Repair order sections (11 components)
- `TaxClass/` - Tax class management

**Frontend Components** - Use full-page Livewire components for better UX

### `/app/Models`

Eloquent models represent database tables.

**Features:**
- Extend `BaseModel`
- Soft deletes
- Audit trails
- Relationships
- Scopes

### `/app/Helpers`

Reusable helper classes:
- `AppHelper` - General app utilities, breadcrumbs
- `CategoryHelper` - Category tree operations
- `CurrencyHelper` - Currency formatting
- `FormHelper` - Form field rendering
- `LanguageHelper` - Language/translation utilities
- `MediaHelper` - Media file handling
- `NotificationHelper` - Notification utilities
- `SettingHelper` - Settings access
- `TaxHelper` - Tax calculations

### `/app/Traits`

Reusable model traits:
- `HasMeta` - Key-value metadata storage
- `HasSafeCode` - Unique code generation
- `HasSlug` - URL-friendly slug generation
- `HasStatus` - Status management
- `HasStockManagement` - Stock operations (Part model)
- `ManagesPartStock` - Part stock in orders (RepairOrder model)
- `RepairOrderPermissions` - Permission checking

### `/app/Settings/Pages`

Setting page definitions:
- `GeneralSettingPage` - Basic settings
- `CompanySettingPage` - Company info
- `EmailSettingPage` - Email config
- `TaxSettingPage` - Tax settings
- `FinanceSettingPage` - Currency settings
- `InventorySettingPage` - Stock settings
- `AuthenticationSettingPage` - Login settings

### `/resources/views`

Blade templates for rendering HTML.

**Admin Views** (`/admin`)
- Admin panel UI
- Located: `repair-core/resources/views/admin`

**Frontend Views** (`/frontend`)
- Customer-facing UI
- Located: `repair-core/resources/views/frontend`

**Livewire Views** (`/livewire`)
- Livewire component views

### `/database/migrations`

Database schema definitions.

**Features:**
- Version-controlled schema
- Timestamps on all tables
- Soft deletes
- Audit columns (createdBy, updatedBy)
- No foreign keys

### `/public_html/themes`

Frontend assets organized by theme.

**Admin Theme**
- Bootstrap 5.3
- Alpine.js
- Custom admin styles

**Frontend Theme**
- Responsive design
- Customer-facing styles

## Configuration Files

### `/config`

Laravel configuration files:
- `app.php` - Application settings
- `database.php` - Database connections
- `mail.php` - Email settings
- `auth.php` - Authentication
- `services.php` - Third-party services

### Environment Files

`.env` - Environment-specific configuration:
- Database credentials
- API keys
- Debug mode
- App URL

## Asset Management

### Admin Assets

**Location:** `public_html/themes/admin`

**Build:**
```bash
cd public_html/themes/admin
npm run build
```

### Frontend Assets

**Location:** `public_html/themes/frontend`

**Build:**
```bash
cd public_html/themes/frontend
npm run build
```

## Storage Directories

### `/storage/app`

Application file storage:
- User uploads
- Generated files
- Private files

### `/storage/logs`

Application logs:
- Laravel logs
- Error logs
- Custom logs

### `/storage/framework`

Framework storage:
- Cache
- Sessions
- Views

## Testing Structure

### `/tests/Feature`

Feature tests for application functionality.

### `/tests/Unit`

Unit tests for individual components.

---

Next: [Database Design](database-design.md)
