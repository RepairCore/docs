# Helpers

RepairCore provides several helper classes and functions for common operations.

## Helper Classes

### FormHelper

Located at `App\Helpers\FormHelper`. Renders form fields with consistent styling.

```php
use App\Helpers\FormHelper;

// Text input
FormHelper::text('name', 'Name', $value, ['required' => true]);

// Email input
FormHelper::email('email', 'Email', $value);

// Password input
FormHelper::password('password', 'Password');

// Textarea
FormHelper::textarea('description', 'Description', $value, ['rows' => 5]);

// Select
FormHelper::select('status', 'Status', $options, $selected);

// Select2 (Alpine.js based remote select)
FormHelper::select2('customer_id', 'Customer', [
    'url' => route('admin.customers.search'),
    'placeholder' => 'Search customer...',
    'selected' => $customer,
]);

// Checkbox
FormHelper::checkbox('is_active', 'Active', $checked);

// Radio
FormHelper::radio('type', 'Type', $options, $selected);

// File upload
FormHelper::file('image', 'Image', ['accept' => 'image/*']);

// Date picker
FormHelper::date('due_date', 'Due Date', $value);

// Number input
FormHelper::number('quantity', 'Quantity', $value, ['min' => 0]);
```

### SettingHelper

Located at `App\Helpers\SettingHelper`. Access application settings.

```php
// Get setting value
$value = setting_item('company_name', 'Default Company');

// Check if setting exists
if (setting_item('feature_enabled')) {
    // Feature is enabled
}
```

### CurrencyHelper

Located at `App\Helpers\CurrencyHelper`. Format currency values.

```php
// Format currency
$formatted = format_currency(1500000);
// Output: "1,500,000 ₫" (based on settings)

// Get currency symbol
$symbol = currency_symbol();

// Get decimal places
$decimals = currency_decimals();
```

### TaxHelper

Located at `App\Helpers\TaxHelper`. Tax calculation functions.

```php
// Check if tax enabled
if (tax_enabled()) {
    // Apply tax
}

// Get default tax classes
$partsTax = get_default_tax_class_for_parts();
$servicesTax = get_default_tax_class_for_services();

// Get tax class by ID
$taxClass = get_tax_class($id);

// Calculate tax
$taxAmount = calculate_tax($amount, $taxClass);

// Get tax data for item
$taxData = get_tax_data($amount, $taxClassId, 'part');
```

### MediaHelper

Located at `App\Helpers\MediaHelper`. Media and file handling.

```php
// Get media URL
$url = media_url($mediaId);

// Get thumbnail URL
$thumb = media_thumbnail($mediaId, 'small');

// Check if file is image
$isImage = is_image($filename);
```

### NotificationHelper

Located at `App\Helpers\NotificationHelper`. Notification utilities.

```php
// Send notification
send_notification($user, 'order_created', $data);

// Get notification template
$template = get_notification_template('order_status_changed');
```

### CategoryHelper

Located at `App\Helpers\CategoryHelper`. Category tree operations.

```php
// Get category tree
$tree = get_category_tree($type);

// Get category options for select
$options = get_category_options($type);

// Get category path
$path = get_category_path($categoryId);
```

### LanguageHelper

Located at `App\Helpers\LanguageHelper`. Language and translation utilities.

```php
// Get available languages
$languages = get_available_languages();

// Get current language
$current = current_language();

// Get language by code
$language = get_language('en');
```

### AppHelper

Located at `App\Helpers\AppHelper`. General application helpers.

```php
// Set breadcrumbs
set_breadcrumbs([
    ['label' => __('manage_parts'), 'url' => route('admin.parts.index')],
    ['label' => __('edit_part'), 'url' => null],
]);

// Get app version
$version = app_version();

// Check if demo mode
if (is_demo_mode()) {
    // Restrict certain actions
}
```

## Global Helper Functions

These functions are available globally without importing.

### Settings

```php
setting_item($key, $default = null)
```

### Currency

```php
format_currency($amount)
currency_symbol()
currency_decimals()
```

### Tax

```php
tax_enabled()
tax_rate()
tax_name()
calculate_tax($amount, $taxClass = null)
get_tax_data($amount, $taxClassId, $itemType)
```

### Breadcrumbs

```php
set_breadcrumbs(array $breadcrumbs)
```

## Helper File Locations

```
repair-core/app/Helpers/
├── AppHelper.php
├── CategoryHelper.php
├── CurrencyHelper.php
├── FormHelper.php
├── LanguageHelper.php
├── MediaHelper.php
├── NotificationHelper.php
├── SettingHelper.php
└── TaxHelper.php
```

## Creating Custom Helpers

### 1. Create Helper File

```php
<?php
// app/Helpers/CustomHelper.php

if (!function_exists('my_helper_function')) {
    function my_helper_function($param)
    {
        // Implementation
        return $result;
    }
}
```

### 2. Register in composer.json

```json
{
    "autoload": {
        "files": [
            "app/Helpers/CustomHelper.php"
        ]
    }
}
```

### 3. Run Composer Dump

```bash
composer dump-autoload
```

---

Next: [Validation](validation.md)
