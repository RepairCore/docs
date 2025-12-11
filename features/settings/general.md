# General Settings

RepairCore provides a comprehensive settings system organized into multiple pages.

## Settings System

Settings are managed through dedicated Setting Pages located at `App\Settings\Pages\`.

### Available Setting Pages

| Page | Route | Description |
|------|-------|-------------|
| General | `admin/settings/general` | Basic application settings |
| Company | `admin/settings/company` | Company information |
| Email | `admin/settings/email` | Email configuration |
| Tax | `admin/settings/tax` | Tax classes and defaults |
| Finance | `admin/settings/finance` | Currency and financial settings |
| Inventory | `admin/settings/inventory` | Stock management settings |
| Authentication | `admin/settings/authentication` | Login and security settings |
| User | `admin/settings/user` | User-related settings |
| Homepage | `admin/settings/homepage` | Homepage configuration |
| Footer | `admin/settings/footer` | Footer content |

## General Settings

Navigate to **Admin > Settings > General**.

### Application Settings

| Setting | Description |
|---------|-------------|
| site_name | Application/site name |
| site_tagline | Site tagline/description |
| timezone | Default timezone |
| date_format | Date display format |
| time_format | Time display format |

## Company Settings

Navigate to **Admin > Settings > Company**.

### Company Information

| Setting | Description |
|---------|-------------|
| company_name | Legal company name |
| company_address | Business address |
| company_phone | Contact phone |
| company_email | Contact email |
| company_website | Company website URL |
| company_logo | Logo image |
| tax_number | Tax registration number |

### Warranty Settings

| Setting | Description |
|---------|-------------|
| warranty_default_months | Default warranty period |
| warranty_policy | Warranty policy text |
| warranty_terms | Warranty terms and conditions |

## Finance Settings

Navigate to **Admin > Settings > Finance**.

### Currency Settings

| Setting | Description |
|---------|-------------|
| currency_code | Currency code (e.g., VND, USD) |
| currency_symbol | Currency symbol (e.g., ₫, $) |
| currency_position | Symbol position (before/after) |
| decimal_places | Number of decimal places |
| thousand_separator | Thousand separator character |
| decimal_separator | Decimal separator character |

## Inventory Settings

Navigate to **Admin > Settings > Inventory**.

### Stock Settings

| Setting | Description |
|---------|-------------|
| stock_tracking_enabled | Enable stock tracking |
| allow_backorder | Allow backorders when out of stock |
| low_stock_notification | Send low stock alerts |
| default_low_stock_threshold | Default low stock level |

## Email Settings

Navigate to **Admin > Settings > Email**.

### SMTP Configuration

| Setting | Description |
|---------|-------------|
| mail_driver | Mail driver (smtp, sendmail, etc.) |
| mail_host | SMTP host |
| mail_port | SMTP port |
| mail_username | SMTP username |
| mail_password | SMTP password |
| mail_encryption | Encryption (tls, ssl) |
| mail_from_address | Default from address |
| mail_from_name | Default from name |

## Authentication Settings

Navigate to **Admin > Settings > Authentication**.

### Login Settings

| Setting | Description |
|---------|-------------|
| allow_registration | Allow new user registration |
| require_email_verification | Require email verification |
| enable_social_login | Enable social login |
| enable_2fa | Enable two-factor authentication |

## Accessing Settings

### In Code

```php
// Get setting value
$value = setting_item('company_name', 'Default Company');

// Check boolean setting
if (setting_item('allow_backorder')) {
    // Backorder is allowed
}
```

### In Blade Templates

```blade
{{ setting_item('company_name') }}
{{ setting_item('currency_symbol') }}
```

## Creating Setting Pages

Setting pages extend a base class and define their fields:

```php
<?php

namespace App\Settings\Pages;

class CustomSettingPage
{
    public static function slug(): string
    {
        return 'custom';
    }
    
    public static function title(): string
    {
        return __('custom_settings');
    }
    
    public static function fields(): array
    {
        return [
            [
                'name' => 'custom_field',
                'label' => __('custom_field'),
                'type' => 'text',
                'default' => '',
            ],
        ];
    }
    
    public static function view(): string
    {
        return 'admin.settings.pages.custom';
    }
}
```

---

Next: [Company Information](company.md)
